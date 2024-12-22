# Create an array of CPU frequencies in GHz

## Command:
```
$ cpus=($({ echo scale=2; awk '/cpu MHz/ {print $4 " / 1000"}' /proc/cpuinfo; } | bc))
```

## Explanation:
Explanation

The awk command takes the input from /proc/cpuinfo, matches lines containing "cpu MHz", and appends the " / 1000" to the CPU frequency, so it's ready for piping to bc
The echo scale=2 is for bc, to get floating point numbers with a precision of maximum two decimal points
Group the echo scale=2 and the awk for piping to bc, by enclosing the commands within { ...; }
Run the commands in a $(...) subshell 
Wrap the subshell within (...) to store the output lines as an array

From the cpus array, you can extract the individual CPU values with:
cpu0=${cpus[0]}
cpu1=${cpus[1]}
cpu2=${cpus[2]}
cpu3=${cpus[3]}

If you don't need the values in GHz, but MHz is enough, then the command is a lot simpler:
cpus=($(awk '/cpu MHz/ {print $4}' /proc/cpuinfo))

## Limitations:
Limitations
Arrays are Bash specific, might not work in older /bin/sh.
/proc/cpuinfo exists only in Linux.

