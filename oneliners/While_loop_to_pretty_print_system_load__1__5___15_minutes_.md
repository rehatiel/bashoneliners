# While loop to pretty print system load (1, 5 & 15 minutes)

## Command:
```
$ while [ 1 == 1 ]; do  cat /proc/loadavg | awk '{printf "1 minute load: %.2f\n", $(NF-5)}' && cat /proc/loadavg |awk '{printf "5 minute load: %.2f\n", $(NF-3)}' && cat /proc/loadavg |awk '{printf "15 minute load: %.2f\n", $(NF-2)}'; sleep 3; date; done
```

## Explanation:
Explanation
top is great but this will make it easier to read and makes it easy to pipe to text file for historical review.
kill with ctrl+c

## Limitations:
Limitations
/proc/loadavg is only available in Linux.

