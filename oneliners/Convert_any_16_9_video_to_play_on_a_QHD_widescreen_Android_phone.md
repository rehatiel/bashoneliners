# Convert any 16:9 video to play on a QHD widescreen Android phone

## Command:
```
$ ffmpeg -i $1 -y -threads 0 -subq 6 -deinterlace -level 30 -f mp4 -acodec libfaac -ab 160k -ar 24000 -ac 2 -vcodec libx264 -b 1000k -maxrate 1000k -bufsize 2000k -rc_eq 'blurCplx^(1-qComp)' -qcomp 0.6 -qmin 10 -qmax 51 -qdiff 4 -coder 0 -refs 2 -flags +loop -vol 256 -trellis 1 -me_method umh -async 1 $2
```

## Explanation:
Explanation
The Android video player is somewhat fussy about the formats it can play. This ffmpeg script will take any movie file in 16:9 widescreen format and convert it into a form that can be played on one of the current leading QHD phones such as HTC Sensation, Samsung Galaxy S2 or Motorola Atrix. Files that are merely marked as widescreen (e.g. DVD VOBs) will have to be processed into a true widescreen format such as .m2t first.
Parameters:
$1 the input file
$2 the output file
Output file suffix should be .mp4
Requires:
ffmpeg and codecs

## Limitations:
No limitations specified

