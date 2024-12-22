# openiduser171

## Command:
```
$ wmctrl -pl | grep $(pidof mpv) | cut -d'-' -f2-
```

## Explanation:
Explanation
wmctrl -l lists all open windows (works with several window managers), -p includes the unique process ID of each window in the list. grep $(pidof mpv) matches the line that contains the process ID of mpv. cut -d'-' -f2- prints everything after the the first delimiter '-' (from the second onwards), which just leaves the title bit.

## Limitations:
Limitations
Only works with one instance of mpv running. It's intended use is to share what film or series you are watching and you don't usually watch more than one thing at a time.

