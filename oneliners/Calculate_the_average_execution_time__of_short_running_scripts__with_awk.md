# Calculate the average execution time (of short running scripts) with awk

## Command:
```
$ for i in {1..10}; do time some_script.sh; done 2>&1 | grep ^real | sed -e s/.*m// | awk '{sum += $1} END {print sum / NR}'
```

## Explanation:
Explanation

The for loop runs some_script.sh 10 times, measuring its execution time with time
The stderr of the for loop is redirected to stdout, this is to capture the output of time so we can grep it
grep ^real is to get only the lines starting with "real" in the output of time
sed is to delete the beginning of the line up to minutes part (in the output of time)
For each line, awk adds to the sum, so that in the end it can output the average, which is the total sum, divided by the number of input records (= NR)

## Limitations:
Limitations
The snippet assumes that the running time of some_script.sh is less than 1 minute, otherwise it won't work at all.
Depending on your system, the time builtin might work differently. 
Another alternative is to use the time command /usr/bin/time instead of the bash builtin.

