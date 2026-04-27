# raw/youtube-transcripts/

Transcripts of YouTube videos — text only. Don't store the video file here.

## What belongs here

- Auto-caption transcripts pulled from YouTube
- Whisper transcripts of downloaded audio when captions are missing or low-quality
- Hand-cleaned transcripts of important talks/lectures

## Where to export from

- **YouTube UI** — under the video, `··· → Show transcript`, then copy.
- **yt-dlp** — `yt-dlp --write-auto-sub --skip-download --sub-format vtt <url>` and convert the `.vtt` to plain text.
- **NoteGPT, Tactiq, Glasp** — browser extensions that grab the transcript with one click.
- **No captions available?** Download the audio with `yt-dlp -x --audio-format mp3 <url>` and run it through Whisper.

Filename convention: `YYYY-MM-DD-channel-title-slug.md` with a header containing the channel, title, and full URL.
