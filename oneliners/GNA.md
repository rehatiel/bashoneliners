# GNA

## Command:
```
$ export psid=$(pgrep -f libflashplayer.so); cp /proc/$psid/fd/$(lsof -p $psid | grep eleted | awk {' print $4 '} | sed -e "s/[a-z]//g") saved.flv
```

## Explanation:
Explanation
first get the process id of the chome browser process which runs the flashplayer
export it to a variable to be used later. Then we get in subshell the filedescriptor which is marked deleted and construct the /proc path for the in memory fileimage and copy it to the file named saved.flv

## Limitations:
Limitations
IMPORTANT: only one video should be open to play in chrome

