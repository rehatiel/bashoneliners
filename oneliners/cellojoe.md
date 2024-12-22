# cellojoe

## Command:
```
$ lsof / | awk '{ if($7 > 1048576) print $7/1048576 "MB" " " $9 " " $1 }' | sort -n -u | tail
```

## Explanation:
Explanation
Show the largest 10 currently open files, the size of those files in Megabytes, and the name of the process holding the file open.

## Limitations:
No limitations specified

