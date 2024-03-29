# Video Lyrics in Advanced SubStation Alpha (.ass)

## Step 1
Install [FFmpeg](https://ffmpeg.org/) for your operating system, if not already installed. I'm using [Linux Fedora Workstation](https://getfedora.org).
```bash
sudo dnf install ffmpeg
```

## Step 2
Install [libass](https://github.com/libass/libass) for your operating system, if not already installed.
```bash
sudo dnf install libass
```

## Step 3
Install [finale lyrics fonts](https://packages.fedoraproject.org/pkgs/makemusic-finale-fonts/finale-lyrics-fonts/) or use any fonts.
```bash
sudo dnf list finale-lyrics-fonts
```

## Step 4
Download background image, audio & lyrics from the web. For the lyrics, I'm using [Advanced SubStation Alpha (.ass)](https://github.com/jfcherng-sublime/ST-ASS) format. [SubRip (.srt)](https://en.wikipedia.org/wiki/SubRip) also works. See more about [subtitles](https://www.matroska.org/technical/subtitles.html).

## Step 5
Sync audio and lyrics to your liking either manually or from the web in your .ass file. Here are [some examples](https://hhsprings.bitbucket.io/docs/programming/examples/ﬀmpeg/subtitle/ass.html) or you can download [one of mine](https://github.com/mcarlos101/Lyrics/blob/main/1980s/Metal/Megadeth/Megadeth-The-Conjuring-Lyrics.ass).

## Step 6
Create lyric video from background image, audio & lyrics (.ass) to H265 or H264. I'm using H264 because [Vimeo](https://vimeo.com/watch) converted my H265 to H264.
```bash
ffmpeg -loop 1 -i bg.jpg -i audio.m4a -vf subtitles=lyrics.ass -c:v libx265 -c:a copy -shortest video-lyrics.mp4
```

## Step 7
Test the mp4 in your media player. I'm using [VLC media player](https://www.videolan.org/).

# Here are some examples in Vimeo:
1. [Megadeth - The Conjuring Lyrics](https://vimeo.com/927762755)
1. [Entombed - Drowned Lyrics](https://vimeo.com/928069805)
1. [Fear Factory - Zero Signal Lyrics](https://vimeo.com/928867241)
