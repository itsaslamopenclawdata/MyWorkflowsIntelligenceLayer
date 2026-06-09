---
title: "Road to 5 Million Tokens: Breaking Barriers in Long Context Training — Max Ryabinin, Together AI"
channel: "AI Engineer"
channel_slug: "ai-dot-engineer"
channel_id: "UCLKPca3kwwd-B59HNr-_lvA"
published: "2026-06-08"
duration_seconds: 950
video_id: "TUnPNY4E2fw"
url: "https://www.youtube.com/watch?v=TUnPNY4E2fw"
language: "en"
tags: [ai, ai engineer, ai engineering, software development, tech, startups]
transcript_status: "full"
generated_by: "channels-youtube-content"
generated_on: "2026-06-09"
---
# Road to 5 Million Tokens: Breaking Barriers in Long Context Training — Max Ryabinin, Together AI

**Channel:** AI Engineer  **Published:** 2026-06-08  **Duration:** 15:50  **Watch:** https://www.youtube.com/watch?v=TUnPNY4E2fw

## TL;DR

Max Ryabinin from Together AI walks the full stack for training a long-context model. LLaMA 3B at 3M tokens fails on 8xH100 before you start — model parameters alone exhaust memory. The floor stack: FSDP + DeepSpeed Ulysses (8x activation reduction) + activation checkpointing (8x) + CPU offload + chunked sequence training. The novel contribution is *Untied Ulysses* — chunk attention heads further and reuse the buffers across iterations, cutting activation memory with negligible throughput cost. At 8B and 32B scale, this matches the most memory-optimized baselines while pushing sequence length 25% further than prior Ulysses. Inference implication: long-context training unlocks long-context product design.

## Key Insights

- **Why long context** (00:02:00) — agents want unbounded context; video generation needs multi-frame temporal consistency (frames-per-second quickly eat tokens). Both push context length into the millions.
- **The two bottlenecks** (00:03:55) — (1) quadratic compute in attention (pairwise interactions across all sequence elements); (2) linear memory growth that's still hard to deal with.
- **Standard LLaMA 3B at 3M tokens on 8xH100 fails before you start** (00:05:30) — model parameters alone exhaust GPU memory. The memory budget for activations and optimizer states on top is a non-starter.
- **The full stack** (00:07:00) — fully sharded data parallelism + DeepSpeed Ulysses context parallelism (**8x activation reduction**) + activation checkpointing (**another 8x**) + CPU offloading of transformer block inputs + chunked sequence training to avoid 3M-token-wide buffers.
- **Untied Ulysses — the novel contribution** (00:11:00) — go deeper into context parallelism: instead of allocating one large buffer per attention head group, chunk the heads further and reuse those buffers across iterations. Cuts activation memory with negligible throughput impact.
- **The result** (00:14:00) — at both 8B and 32B scale, results match the most memory-optimized transformer training baselines while pushing sequence length **25% further** than prior Ulysses implementations.

## Notable Quotes

> "As you continue scaling your context, your memory keeps growing linearly, which is not as bad, but still pretty difficult to deal with, unless you apply a range of specific techniques." — 00:04:15
> "Untied Ulysses: chunk the heads further and reuse those buffers across iterations, cutting activation memory with negligible throughput impact." — 00:11:30
> "At both 8B and 32B scale the results match the most memory-optimized transformer training baselines while pushing sequence length 25% further than prior Ulysses implementations." — 00:14:00

## Tools and Resources Mentioned

- **DeepSpeed Ulysses** (deepspeed.readthedocs.io) — vendor: Microsoft / open-source — sequence parallelism for long-context training
- **Fully Sharded Data Parallelism (FSDP)** — vendor: PyTorch — sharded model/optimizer states across GPUs
- **Activation Checkpointing** — vendor: PyTorch — recompute activations on backward pass to save memory
- **Together AI** (together.ai) — vendor: Together AI — AI-native cloud, runs the long-context training stack described

## GitHub Repos and URLs Referenced

- (none referenced)

## Action Items

- [ ] If planning to fine-tune a long-context model: budget for FSDP + Ulysses + checkpointing + CPU offload. Get all four wired before training starts.
- [ ] Track Untied Ulysses for upstreaming into DeepSpeed / Hugging Face accelerate — the 25% sequence-length win is worth adopting.
- [ ] For inference workloads: long-context training enables long-context inference. Start product-designing for 1M+ token inputs.

## Open Questions

- How does Untied Ulysses interact with KV-cache compression / paged attention at inference time? (Inference angle not covered.)
- What are the multi-node scaling characteristics? (Talk stays inside a single 8xH100 node.)

---

<details>
<summary><b>Raw Transcript</b> (click to expand — full 15:50 transcript)</summary>

0:14 Everyone, my name is Max. I am VP of
0:17 research and development at Together AI.
0:19 And today, I'm going to tell you about
0:22 our research project, which is called
0:25 Road to 5 million sequence length,
0:27 breaking memory barriers in context
0:28 parallelism.
0:30 So, to begin,
0:32 uh I'll first say a few words about
0:34 Together AI and who we are.
0:36 Together AI is an AI native cloud, which
0:39 provides
0:41 services and infrastructure for AI
0:44 developers and builders at all stages of
0:46 development, starting from
0:48 uh creating a model, where you just
0:50 might need a GPU cluster with heavily
0:53 optimized computes and uh highly
0:56 reliable uh
0:58 systems,
0:59 uh all the way through model shaping,
1:01 where you can take existing models and
1:03 customize them for your tasks in terms
1:05 of performance, in terms of speed, in
1:08 terms of quality, through services such
1:10 as the fine-tuning or uh
1:13 reinforcement learning.
1:15 Also, we are an inference provider, so
1:19 if you have an app which is reliant on
1:22 open-source model inference,
1:25 uh you can uh work with us and we'll
1:28 provide you with the fastest way to
1:30 launch and use AI models
1:33 with more than 200 models in our
1:35 portfolio,
1:36 uh options for deployment, which include
1:39 serverless and dedicated inference, and
1:42 a ton of advanced optimizations, which I
1:45 will not be able to speak about today.
1:47 Um the purpose of this talk is
1:51 uh focused on model training,
1:53 customization, and fine-tuning in
1:55 particular.
1:56 And
1:57 uh I'll start by asking a question. Uh I
2:00 think in the last few months or like at
2:04 least a year or so, we're seeing a lot
2:06 of interest in the community, uh both on
2:08 the system side and on the research
2:10 side, in training long context models.
2:13 Um the primary reasons for that are
2:16 twofold, I would say. First of all, with
2:19 the uh
2:20 like explosion in popularity of agents,
2:22 you can see a lot of different
2:24 applications where you might want to put
2:27 as many tokens as you want in your
2:29 context, and you want the model to
2:32 leverage that context effectively.
2:35 Um second, with the development of
2:37 applications such as video generation,
2:40 you might often need to keep track of
2:43 multiple
2:45 uh like
2:46 uh different frames, which or like even
2:49 uh multiple frames per second, which can
2:52 um occupy quite a few tokens in your
2:55 context pretty quickly.
2:57 And you also need models that have good
3:00 uh sense of uh temporal consistency,
3:02 which means that they are able to see
3:05 what was happening a few seconds or
3:07 ideally a few minutes ago.
3:10 Um to do that all effectively, you need
3:13 to make sure that the models are able to
3:16 process that context and work with it
3:19 correctly at the training time.
3:22 Um but even if you're not at the scales
3:26 of like millions of
3:28 uh tokens in the context length, it's
3:31 still quite important to understand
3:33 where the memory goes, because who
3:35 knows, maybe you might be able to
3:37 reinvest it in some other ways and speed
3:40 up your training overall.
3:42 So, the problem here is that if you are
3:46 taking a standard transformer-based
3:49 language model and trying to extend its
3:51 context, you can run
3:54 into two bottlenecks.
3:56 Bottleneck number one is that you are
3:59 faced with quadratic computation,
4:01 because uh long story short, for
4:04 transformer-based models,
4:06 uh you have pairwise interactions across
4:09 all the elements in a sequence.
4:11 The second problem is more insidious,
4:14 one might say.
4:15 Uh
4:16 as you continue scaling your context,
4:19 your memory keeps growing linearly,
4:22 which is not as bad, but still pretty
4:25 difficult to deal with, unless you apply
4:28 a range of specific techniques.
4:30 Um and this is an example from Hugging
4:34 Face's blog post on model training,
4:36 which shows that the sequence length
4:40 growth can affect your memory limits
4:43 pretty considerably.
4:46 Um yeah, here's the slide. And our goal
4:50 of that project was to see how far
4:54 exactly we are able to get with a range
4:57 of existing techniques that are pretty
4:59 well known to some in the community, as
5:02 well as some further optimizations that
5:05 we wanted to leverage to push this a bit
5:09 further ahead.
5:11 So,
5:12 um let's say you're taking a model which
5:14 is a standard Llama 3B architecture,
5:17 you're trying to fit 3 million train
5:20 tokens into your context, and you're
5:22 taking uh all of this
5:25 on an 8
5:27 uh x H100 GPU node.
5:29 Um the first stage you'll see is that
5:33 even with uh just model parameters,
5:36 you're not able to fit uh
5:38 it into the GPU.
5:40 Uh you run out of memory just by trying
5:42 to place the model.
5:43 Of course, the next stage is to apply
5:46 fully sharded data parallelism, where
5:48 all the parameters are like basically
5:50 chunked across the eight GPUs that you
5:52 have, which is great, but uh still
5:55 doesn't solve the problem. You see that
5:58 uh the memory usage for the model drops
6:00 quite significantly, but you still are
6:04 running out of memory because of all the
6:06 attention activations.
6:08 The next point that
6:10 uh we've leveraged, and I encourage you
6:12 to use as well, is
6:15 uh taking advantage of uh context
6:18 parallelism. In particular, there is a
6:20 pretty well-known technique called
6:22 DeepSpeed Ulysses, first
6:24 uh introduced by Microsoft.
6:26 The idea is that instead of computing
6:29 all of your multi-head attention like on
6:32 every GPU separately for the whole
6:35 sequence, you can do something more
6:37 clever. In particular, you can try to
6:41 compute the attention for different
6:44 heads at different points in time, uh or
6:46 like on different GPUs, uh through
6:49 communicating these activations as uh
6:52 they are required, in such a way that
6:55 one GPU is only responsible for one
6:59 attention head here, but it's still
7:01 computing the attention over the whole
7:03 sequence.
7:04 Um that technique is
7:06 quite effective at uh addressing the
7:08 problem, and it also allows you to
7:11 utilize the best possible attention
7:13 implementation, like Flash Attention 1 2
7:16 3 4, um
7:18 to optimize that part of the
7:21 computation. And then you aggregate the
7:23 results as uh you would have
7:26 uh previously.
7:27 So, if you apply Ulysses context
7:29 parallelism, the utilization drops quite
7:32 significantly, like approximately 8x uh
7:36 here, as uh it should, but we are still
7:40 quite far from our goal of being able to
7:42 fit that onto just a single
7:46 uh H100 node.
7:48 So, what happens next is that we can try
7:52 to recompute the activations as they uh
7:55 are needed to us at the backward pass.
7:58 That technique is known as activation
8:00 checkpointing, and uh it's available in
8:03 pretty much all of the deep learning
8:05 frameworks these days that you could
8:08 use. You just need to enable it in a
8:10 correct way that does not
8:12 uh
8:13 impose too much of a computational
8:15 burden on you.
8:18 Um with that, with activation
8:20 checkpointing, you can drop the
8:23 activation usage by like a further
8:24 factor of eight,
8:26 but still something else needs to be
8:29 done.
8:30 Uh the next optimization is
8:35 um also connected to the storage of
8:37 activations. You can try to uh
8:42 store some of the inputs to each
8:44 transformer block, not on the GPU, but
8:47 instead offload them to CPU when they
8:50 are not required.
8:51 Uh this is not very impactful for the
8:55 performance, because you can offload uh
8:58 it and prefetch when you are trying to
9:02 backpropagate to that to the
9:03 corresponding layer. Um this
9:05 optimization, to the best of our
9:07 knowledge, was first implemented uh by
9:10 Unsloth, and uh it allows you to
9:13 drastically expand the context window.
9:16 Um the next point is that you're getting
9:20 uh with offloading next to 37
9:24 uh gigabytes of data, but then comes the
9:26 other part of offload memory usage.
9:29 Uh what happens next is that you can
9:31 essentially tile all all of the
9:33 computations across the
9:36 sequence length in case they are
9:38 element-wise. So, all the loss
9:40 computations, all the MLPs, they can be
9:43 chunked to avoid creating these huge
9:46 buffers that would be 3 million along
9:49 one of the dimensions.
9:51 Um that's Arctic sequence length
9:53 training, and even with these
9:55 optimizations, you are finally getting
9:57 to a point where 3 million is possible.
10:00 But, what if you wanted to go further?
10:04 And here we actually need to do
10:07 something else, which is the primary
10:11 optimization we've done in our work
10:13 dubbed the Untitled Ulysses. And you
10:17 could describe it as a further deeper
10:21 analysis and expansion of this context
10:24 parallelism technique.
10:26 So, what we found was that even trying
10:29 to compute one set of heads at a time
10:33 is already enough to saturate the
10:36 computational capacity of the GPU with
10:39 within one iteration. Which means that
10:42 if you have multiple different heads
10:44 scheduled to be executed on one GPU, you
10:48 can divide it in chunks and then
10:50 essentially iterate through these chunks
10:53 over time. So, we have one group of
10:56 heads which are being recomputed, then
10:58 you compute attention over them, you
11:01 store the partial result, then you
11:04 follow up with the next stage, which can
11:06 reuse all the buffers you've allocated
11:09 at the previous stage. Um so, the
11:12 advantage here is that instead of
11:13 allocating this huge buffer as you would
11:16 have before like here in this slide,
11:19 you allocate a buffer which is smaller,
11:22 but you reuse it across like two or more
11:26 different iterations.
11:28 And that allows it to further save on
11:31 the activation memory for your training
11:34 without any significant impact to the
11:37 throughput at small scales. So, here you
11:40 can see the results that we've measured
11:43 across different context parallelism
11:45 techniques. As you can see, both at the
11:47 8 billion scale and at the 32 billion
11:50 scale, we are matching quite closely the
11:55 most memory optimized implementations of
11:57 transformer training while being able to
12:00 scale even further like 5 million tokens
12:03 and sometimes even being more performant
12:06 at small at shorter context lengths.
12:10 Um the relation between the chunk size
12:14 or the number of heads you compute at
12:15 the same time and the throughput is
12:18 quite straightforward. So, if your chunk
12:21 is larger, your memory utilization is
12:23 higher, but at the same time you can run
12:27 the whole model a bit faster.
12:29 Um so, by stacking all of these
12:32 techniques together and applying U-Pipe
12:34 on top, you can, for example,
12:37 free up a bit of additional memory in
12:40 your training if you need it and
12:42 reinvest it somewhere else, for example,
12:45 among the stages. Or
12:47 you could say that we're interested in
12:49 training across not 3 by 5 million
12:52 context lengths and then
12:54 you pipe is the technique that will save
12:56 you
12:57 by contrast to everything else.
13:00 So,
13:01 as a takeaway,
13:03 I think one of the things that
13:06 could be
13:07 quite insightful here is that training
13:10 models with large context lengths is a
13:13 very interesting and challenging goal,
13:16 but the bottlenecks might appear where
13:18 you least expect. So, tooling like the
13:21 PyTorch profiler, which
13:23 we
13:25 elaborate on on in our paper, or other
13:28 or other techniques can help you a lot.
13:31 And also check out our paper for more
13:34 results. All of that is public at the
13:36 moment and we have an upcoming thread
13:39 which will illustrate the method in more
13:42 depth.
13:43 Thank you very much for listening and
13:45 now we are ready for questions.
13:52 Thank you.
13:56 Do you guys have any questions cuz we're
13:58 together and I am employees.
14:01 So, who did you join it from the middle
14:03 so
14:04 we lack some certain context?
14:07 I'm just curious about the
14:09 so the QKV that was quantization
14:12 parameters is that correctly
14:15 Uh not exactly. It was just the query,
14:18 key, and value matrices of the
14:20 transformer layer. So,
14:23 you multiply them here in the attention
14:25 part, which
14:27 creates most of the complexity because
14:29 all of the queries have to like result
14:31 in all of these pairwise active
14:33 interactions with
14:36 like keys.
14:37 Uh and the problem is that if you have a
14:42 a sequence which is like 3 million in
14:45 length, it means that technically like
14:47 in the standard most vanilla way, you
14:50 would have just like allocated that
14:52 whole big tensor which has 3 million in
14:55 which is 3 million in size
14:57 along one of the axis. And like that's
14:59 pretty significant as you could imagine,
15:02 which means that you have to resort to
15:04 like not just one technique, which is
15:06 U-Pipe, but a range of other approaches
15:09 to somehow help you like uh
15:14 leverage like execute these computations
15:16 without running out of your memory.
15:19 So, yeah, that's the
15:20 key idea and the key challenge of
15:23 working with transformers at the scale.
15:30 Cool.
15:31 Um in that case, thank you very much for
15:33 questions and for listening.


</details>
