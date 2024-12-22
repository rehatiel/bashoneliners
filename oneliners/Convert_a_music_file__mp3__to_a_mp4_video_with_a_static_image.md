# Convert a music file (mp3) to a mp4 video with a static image

## Command:
```
$ ffmpeg -loop_input -i cover.jpg -i soundtrack.mp3 -shortest -acodec copy output_video.mp4
```

## Explanation:
Explanation
Can come handy when you'd like to post a song to YT or somethin' :)
Can be easily wrapped up in a function:
function mp3tovidwithimg() {
  ffmpeg -loop_input -i $1 -i $2 -shortest -acodec copy $3
}

and used like that: 
mp3tovidwithimg cover.jpeg music_track.mp3 output_vid.mp4

## Limitations:
No limitations specified

