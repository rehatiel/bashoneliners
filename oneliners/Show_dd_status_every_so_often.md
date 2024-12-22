# Show dd status every so often

## Command:
```
$ watch --interval 5 killall -USR1 dd
```

## Explanation:
Explanation
The dd command has no progress indicator. While copying large files it may seem like nothing is happening, as dd prints nothing until completed. However, when the dd process receives USR1 signal, it prints I/O statistics to standard error and resumes copying. Here we use killall to send the signal, and we call it with watch to repeat this every 5 seconds, effectively giving a progress indicator to good old dd.
Start in one window the watch:
$ watch --interval 5 killall -USR1 dd

Start copying in another:
$ dd if=/dev/random of=junk bs=1000 count=1000 
dd: warning: partial read (13 bytes); suggest iflag=fullblock
0+2 records in
0+2 records out
21 bytes (21 B) copied, 3.01687 s, 0.0 kB/s
0+3 records in
0+3 records out
29 bytes (29 B) copied, 8.02736 s, 0.0 kB/s

## Limitations:
No limitations specified

