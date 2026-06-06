# YouTube Channels Video Learning

This folder is the intelligence layer for YouTube channels I track. Every new video from a tracked channel is automatically fetched, transcribed, distilled into a structured note, and committed here.

## What this is

- A versioned library of structured notes from YouTube videos
- Built to remove the need to manually watch every video
- Each note compresses a video into a 3-minute read
- Full transcript is stored alongside, available on demand
- The repo is the source of truth, searchable and diffable

## Folder structure

```
YoutubeChannelsVideosLearning/
├── README.md                      # this file
├── INDEX.md                       # auto-regenerated, one line per video
├── CHANNELS.md                    # human-readable channel list
├── channels.json                  # machine-readable channel registry
├── templates/
│   └── video-note.md              # the .md template every note uses
├── channels/
│   ├── [channel-slug]/
│   │   ├── CHANNEL-INFO.md        # channel overview, why tracked
│   │   ├── transcripts/           # raw transcripts, full text
│   │   └── videos/                # structured .md notes
│   │       └── YYYY-MM-DD_slug.md
│   └── ...
└── scripts/                       # pipeline scripts (added in Phase 2)
```

## Tracked channels

See `CHANNELS.md` for the human-readable list.
See `channels.json` for the machine-readable registry used by the cron pipeline.

## How to use this

1. Open `INDEX.md` to see every video, newest first
2. Click into a note for the 3-minute structured summary
3. Expand the `Raw Transcript` section in the note if you need the full text
4. Use the frontmatter tags to grep across all notes

## How a video gets added

1. Cron job polls the YouTube RSS feed for each tracked channel daily
2. New video detected → transcript fetched via `youtube-transcript-api` or local Whisper fallback
3. Transcript + metadata passed to LLM with the `templates/video-note.md` template
4. Note file written to `channels/[slug]/videos/`
5. Raw transcript saved to `channels/[slug]/transcripts/`
6. `channels.json` updated with new `last_seen_video_id`
7. `INDEX.md` regenerated
8. Commit and push to this repo
9. Telegram alert sent with title, channel, 1-line gist, link to note

## Adding a new channel

1. Add entry to `channels.json`
2. Add row to `CHANNELS.md`
3. Create `channels/[slug]/` with `CHANNEL-INFO.md`
4. Run `scripts/backfill_channel.py` to fetch the last 10 videos
5. Commit and push

## Rebuilding notes from existing transcripts

If the template changes or you want to regenerate notes, run `scripts/regenerate_note.py` against any existing transcript. No need to re-fetch from YouTube.
