# Redirect the output of the time builtin command

## Command:
```
$ { time command; } > out.out 2> time+err.out
```

## Explanation:
Explanation

time is a bash builtin command, and redirecting its output does not work the same way as with proper executables
If you execute within braces like above, the output of time will go to stderr (standard error), so you can capture it with 2>time.out
An alternative is to use the /usr/bin/time executable, by referring to its full path. (The path may be different depending on your system.)

## Limitations:
No limitations specified

