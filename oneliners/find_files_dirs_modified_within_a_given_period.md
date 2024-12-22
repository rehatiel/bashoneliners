# find files/dirs modified within a given period

## Command:
```
$ find . -type d -newermt "2019-01-01" \! -newermt "2019-02-01" -exec ls -ld {} \;
```

## Explanation:
Explanation
List all directories that was modified in january (between 2019-01-01 and up til, but not included 2019-02-01).

## Limitations:
No limitations specified

