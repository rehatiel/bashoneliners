# Extract audio only from video files using ffmpeg

## Command:
```
$ ffmpeg -i video.any -vn -acodec libvorbis audio.ogg
```

## Explanation:
Explanation
-i is to specify the input file, which can be any kind of video file, such as mpeg, mkv, flv, and others.
-vn means "no video", effectively extracting audio only.
-acodec libvorbis specifies to encode the audio as ogg. To encode as mp3, use -acodec libmp3lame instead.
See more related tips at this gist.

## Limitations:
Limitations
Requires ffmpeg, a video converter tool.

