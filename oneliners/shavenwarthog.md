# shavenwarthog

## Command:
```
$ for INPUT in *.avi ; do echo "${INPUT%.avi}" ; done | xargs -i -P9  HandBrakeCLI -i "{}".avi -o "{}".mp4
```

## Explanation:
Explanation
This oneliner uses the wonderful Handbrake program to convert videos.  We convert a directory of AVIs at a time, in parallel.
The first three bits ("for INPUT...done |") lists the AVI files in the current directory, then uses a Bash function to strip off the suffix.  It then sends each video file name to the next part.
The next part  of the command (| xargs ...) runs our converter in parallel.  The "-i" flag says take each input (video file name) and stick it in the "{}" parts of the xargs command.  The parallel option lets us run up to 9 commands at the same time ("-P9").
The last part (HandBrakeCLI -i "{}".avi -o "{}".mp4)  converts a single video to MP4 format.  The two open-close curly braces are replaced with xargs, once per input video file.  The first run through will be "HandBrakeCLI -i "input1".avi -o "input1".mp4", next will be "HandBrakeCLI -i "input2".avi -o "input2".mp4", etc.
Enjoy!
Another version of this writeup is on my blog: http://johntellsall.blogspot.com/2013/08/converting-video-for-media-player.html

## Limitations:
Limitations
Converting videos in parallel is confusing as Handbrake overwrites the status for every file -- ignore the screen.
install Handbrake from http://handbrake.fr/
It also has a pretty GUI for those who don't like the terminal :)

