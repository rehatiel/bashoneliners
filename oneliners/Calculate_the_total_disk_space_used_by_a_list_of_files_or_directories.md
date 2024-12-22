# Calculate the total disk space used by a list of files or directories

## Command:
```
$ du -s file1 dir1 | awk '{sum += $1} END {print sum}'
```

## Explanation:
Explanation

This is really simple, the first column is the size of the file or the directory, which we sum up with awk and print the sum at the end.
Use du -sk to count in kilobytes, du -sm to count in megabytes (not available in some systems)

## Limitations:
No limitations specified

