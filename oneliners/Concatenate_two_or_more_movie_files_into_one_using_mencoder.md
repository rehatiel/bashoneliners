# Concatenate two or more movie files into one using mencoder

## Command:
```
$ mencoder cd1.avi cd2.avi -o movie.avi -ovc copy -oac copy
```

## Explanation:
Explanation

You can specify as many files as you want on the command line to process them in sequence.
-ovc copy simply means to copy the video exactly
-oac copy simply means to copy the audio exactly
-o movie.avi is the output file, with all the source files concatenated

## Limitations:
Limitations

mencoder is usually not a standard package
mencoder may be in the same package as mplayer, or maybe not
mencoder has binary packages for Linux, Mac and Windows

See the MPlayer homepage for more info: http://www.mplayerhq.hu/

