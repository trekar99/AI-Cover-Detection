# 🎶 Cover Identification System Using Lyrics

## 📋Task Overview

The challenge: build a system that takes a YouTube music video URL and returns the title and artist of the song by matching the lyrics with a DB of songs.

```
covers = get_covers(youtube_url, k)
```
Where `covers` is a list of dicts with length `k` sorted by score.
```
[
    {"title": "Title 1", "artist": "Artist 1", "score": 95.0},
    {"title": "Title 2", "artist": "Artist 2", "score": 89.5},
    ...
]
```

To achieve this, the program will need to:

Setup:
1. Download a lyrics dataset
2. Extract embeddings for each song's lyrics
3. Create a vector index (database) for fast retrieval of similar lyrics

Then, for each youtube URL (query):

1. Download the youtube video in a temporary file
2. Transcribe the lyrics using the Whisper model
3. Extract the embeddings of the transcribed lyrics
4. Search the top-k similar entries in your vector database and return the song title and artist
