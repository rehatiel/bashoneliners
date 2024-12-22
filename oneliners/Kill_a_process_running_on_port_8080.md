# Kill a process running on port 8080

## Command:
```
$ lsof -i :8080 | awk 'NR > 1 {print $2}' | xargs --no-run-if-empty kill
```

## Explanation:
Explanation
lsof lists open files (ls-o-f, get it?). lsof -i :8080 lists open files on address ending in :8080. The output looks like this
COMMAND  PID     USER   FD   TYPE DEVICE SIZE/OFF NODE NAME
chrome  2619 qymspace  149u  IPv4  71595      0t0  TCP localhost:53878->localhost:http-alt (CLOSE_WAIT)`

We use awk 'NR > 1 {print $2}' to print the second column for lines except the first. The result is a list of PIDs, which we pipe to xargs kill to kill.

## Limitations:
Limitations
The --no-run-if-empty option of xargs is available in GNU implementations, and typically not available in BSD implementations. Without this option, the one-liner will raise an error if there are no matches (no PIDs to kill).

