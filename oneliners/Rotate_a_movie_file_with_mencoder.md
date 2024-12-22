# Rotate a movie file with mencoder

## Command:
```
$ mencoder video.avi -o rotated-right.avi -oac copy -ovc lavc -vf rotate=1
```

## Explanation:
Explanation
mencoder is part of mplayer.
Other possible values of the rotate parameter:

0: Rotate by 90 degrees clockwise and flip (default).
1: Rotate by 90 degrees clockwise.
2: Rotate by 90 degrees counterclockwise.
3: Rotate by 90 degrees counterclockwise and flip.

## Limitations:
No limitations specified

