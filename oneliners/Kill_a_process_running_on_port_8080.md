# Kill a process running on port 8080

## Command:
```
$ lsof -i :8080 | awk '{print $2}' | tail -n 1 | xargs kill
```

## Explanation:
Explanation
lsof lists open files (ls-o-f, get it?). lsof -i :8080 lists open files on address ending in :8080. The output looks like this 
COMMAND  PID     USER   FD   TYPE DEVICE SIZE/OFF NODE NAME
chrome  2619 qymspace  149u  IPv4  71595      0t0  TCP localhost:53878->localhost:http-alt (CLOSE_WAIT)`

We pipe this input through awk to print column 2 using the command awk '{print $2}' to produce the output:
PID
2533

To remote the word PID from this output we use tail -n 1 to grab the last row 2533,
We can now pass this process id to the kill command to kill it.

## Limitations:
Limitations
The --no-run-if-empty option of xargs is available in GNU implementations, and typically not available in BSD implementations. Without this option, the one-liner will raise an error if there are no matches (no PIDs to kill).

