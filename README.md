# Video Lyrics in Advanced SubStation Alpha (.ass)

## Step 1
Install [FFmpeg](https://ffmpeg.org/) for your operating system, if not already installed. I'm using [Fedora Linux Workstation](https://getfedora.org).
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
Use a background image in 1920x1080 resolution for full high definition (FHD) or the resolution of your choice. You may need to edit image with [GIMP](https://www.gimp.org/) or your favorite image editor.

## Step 5
Use [lossless or lossy audio formats](https://riverside.fm/blog/lossless-audio-formats). For this example, I'm using .m4a.

## Step 6
For the lyrics, I'm using [Advanced SubStation Alpha (.ass)](https://github.com/jfcherng-sublime/ST-ASS) format. [SubRip (.srt)](https://en.wikipedia.org/wiki/SubRip) also works. See more about [subtitles](https://www.matroska.org/technical/subtitles.html).

## Step 7
Sync audio and lyrics to your liking either manually or from the web in your .ass file. Here are [some examples](https://hhsprings.bitbucket.io/docs/programming/examples/ﬀmpeg/subtitle/ass.html) or you can download [one of mine](https://github.com/mcarlos101/Lyrics/blob/main/1980s/Metal/Megadeth/Megadeth-The-Conjuring-Lyrics.ass).

## Step 8
Create video lyrics from background image, audio & lyrics (.ass) to H265 or H264. I'm using H264 because [Vimeo](https://vimeo.com/watch) converted my H265 to H264. Use mp4 or mkv for video format. Here's a one [comparison of the two formats](https://videocandy.com/blog/mkv-vs-mp4.html).
```bash
ffmpeg -loop 1 -i bg.jpg -i audio.m4a -vf subtitles=lyrics.ass -c:v libx265 -c:a copy -shortest video-lyrics.mp4
```

## Step 9
Test the mp4 or mkv in your media player. I'm using [VLC media player](https://www.videolan.org/).

# Here are some examples in Vimeo:
1. [Megadeth - The Conjuring Lyrics](https://vimeo.com/927762755)
1. [Entombed - Drowned Lyrics](https://vimeo.com/928069805)
1. [Fear Factory - Zero Signal Lyrics](https://vimeo.com/928867241)
