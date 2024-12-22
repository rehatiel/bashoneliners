# Make the output of the `time` builtin easier to parse

## Command:
```
$ TIMEFORMAT=%R
```

## Explanation:
Explanation
The time builtin prints a summary of the real time, user CPU time and system CPU time spent executing commands, for example:
$ time sleep 1

real    0m1.002s
user    0m0.000s
sys     0m0.002s

If you need to parse this output, it helps to simplify it using the TIMEFORMAT variable. The value %R means "the elapsed time in seconds", for example:
$ TIMEFORMAT=%R
$ time sleep 1
1.004

The complete documentation of the format definition is in man bash, search for TIMEFORMAT.

## Limitations:
No limitations specified

