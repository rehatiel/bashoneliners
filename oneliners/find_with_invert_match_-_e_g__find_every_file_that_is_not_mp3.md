# find with invert match - e.g. find every file that is not mp3

## Command:
```
$ find . -name '*' -type f -not -path '*.mp3'
```

## Explanation:
Explanation
Find is normally used to positively match a pattern, so find . -name '*.mp3' -type f
will match every mp3 file in the current folder and its subfolders.
If you would like to exclude something from these matches, you could use the addition -not -path '<exclude pattern>', which I find much easier than using a pipe with | grep -v.
find . -name '*' -type f -not -path '*.mp3'

## Limitations:
No limitations specified

