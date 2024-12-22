# Convert all flac files in dir to mp3 320kbps using ffmpeg

## Command:
```
$ for FILE in *.flac; do ffmpeg -i "$FILE" -b:a 320k "${FILE[@]/%flac/mp3}"; done;
```

## Explanation:
Explanation
It loops through all files in current directory that have flac extension and converts them to mp3 files with bitrate of 320kpbs using ffmpeg and default codec.

## Limitations:
No limitations specified

