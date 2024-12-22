# Convert all flac files in the current directory to mp3 format using "lame"

## Command:
```
$ for i in *.flac; do flac -c -d "$i" | lame -m j -b 192 -s 44.1 - "${i%.flac}.mp3"; done
```

## Explanation:
Explanation

## Limitations:
No limitations specified

