# Convert m4a files to mp3 using faad and lame

## Command:
```
$ faad -o tmp.wav music.m4a && lame -b 192 tmp.wav music.mp3
```

## Explanation:
Explanation

Step 1: convert m4a to wav using faad
Step 2: convert wav to mp3 using lame
-b 192 is the bitrate

## Limitations:
Limitations
Neither faad nor lame are standard commands.

