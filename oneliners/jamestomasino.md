# jamestomasino

## Command:
```
$ lsof -i :8080 | awk '{l=$2} END {print l}' | xargs kill
```

## Explanation:
Explanation
As before, we're using lsof to find the PID of the process running on port 8080. We use awk to store the second column of each line into a variable l, overwriting it with each line. In the END clause, we're left with the second column of only the last line. xargs passes that as a parameter to the kill command.
The only notable diffirence from the command listed above is the use of awk to also complete the tail -n 1 step. This awk pattern matches the same intended behavior of the script that was using tail. To kill all processes on that port, you could use the NR>1 clause instead of the variable loop.

## Limitations:
No limitations specified

