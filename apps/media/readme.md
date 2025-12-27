---
id: media
name: Media
description: Get transcripts, metadata, and download videos/audio from YouTube and other sources
icon: icon.svg
color: "#7C3AED"

schema:
  content:
    id:
      type: string
      required: true
      description: Unique identifier (video ID, track ID)
    title:
      type: string
      required: true
      description: Title of the content
    creator:
      type: string
      description: Channel name, artist, or uploader
    description:
      type: string
      description: Full description text
    duration:
      type: number
      description: Duration in seconds
    url:
      type: string
      description: URL to the content
    thumbnail:
      type: string
      description: Thumbnail image URL
    view_count:
      type: number
      description: Number of views (if available)
    upload_date:
      type: string
      description: When the content was uploaded/released
    type:
      type: enum
      values: [video, audio, track, episode]
      description: Type of content

  transcript:
    text:
      type: string
      required: true
      description: Full transcript text
    language:
      type: string
      description: Language code (en, es, fr, etc.)

actions:
  metadata:
    description: Get video/audio metadata (title, duration, channel, etc.)
    readonly: true
    params:
      url:
        type: string
        required: true
        description: URL to the content
      connector:
        type: string
        description: Which connector to use (youtube)
    returns: content

  transcribe:
    description: Get transcript/subtitles from a video
    readonly: true
    params:
      url:
        type: string
        required: true
        description: Video URL
      lang:
        type: string
        default: en
        description: Language code (en, es, fr, etc.)
      connector:
        type: string
        description: Which connector to use (youtube)
    returns: transcript

  download:
    description: Download video to Downloads folder
    params:
      url:
        type: string
        required: true
        description: Video URL
      quality:
        type: string
        default: "1080"
        description: Max video height (360, 480, 720, 1080, 1440, 2160)
      connector:
        type: string
        description: Which connector to use (youtube)
    returns:
      path:
        type: string
        description: Path to downloaded file

  audio:
    description: Extract audio as MP3 to Downloads folder
    params:
      url:
        type: string
        required: true
        description: Video URL
      connector:
        type: string
        description: Which connector to use (youtube)
    returns:
      path:
        type: string
        description: Path to downloaded file

instructions: |
  When working with media:
  - Use transcribe to get video transcripts for summarization
  - Use metadata to check video length before downloading
  - Use audio for podcasts/music (extracts mp3)
  - Use lower quality (720, 480) for faster video downloads
  - YouTube URLs: youtube.com/watch?v=..., youtu.be/...
---

# Media

Get transcripts, metadata, and download videos/audio from various sources.

## Requirements

YouTube requires `yt-dlp` to be installed:

```bash
brew install yt-dlp
```

## Actions

| Action | Purpose |
|--------|---------|
| `metadata` | Get video info (title, duration, channel) |
| `transcribe` | Get transcript/subtitles |
| `download` | Download video file |
| `audio` | Extract audio as MP3 |

### metadata

```
Media(action: "metadata", params: {url: "https://youtube.com/watch?v=..."})
```

### transcribe

```
Media(action: "transcribe", params: {url: "https://youtube.com/watch?v=..."})
Media(action: "transcribe", params: {url: "...", lang: "es"})
```

### download

```
Media(action: "download", params: {url: "https://youtube.com/watch?v=..."})
Media(action: "download", params: {url: "...", quality: "720"})
```

### audio

```
Media(action: "audio", params: {url: "https://youtube.com/watch?v=..."})
```

## Connectors

| Connector | Source |
|-----------|--------|
| `youtube` | YouTube videos |

## URL Formats

YouTube accepts:
- `https://www.youtube.com/watch?v=dQw4w9WgXcQ`
- `https://youtu.be/dQw4w9WgXcQ`
