# Find all log files modified 24 hours ago, and zip them

## Command:
```
$ find . -type f -mtime +1 -name "*.log" -exec zip -m {}.zip {} \; >/dev/null
```

## Explanation:
Explanation


-type f: find only files


-mtime +n: file was last modified n*24 hours ago


-name "*.log": filename ends with .log


zip -m {}.zip: compress file into zip, and delete original file


> /dev/null: suppress output

## Limitations:
No limitations specified

