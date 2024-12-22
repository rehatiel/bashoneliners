# View a file with line numbers

## Command:
```
$ grep -n ^ /path/to/file | less
```

## Explanation:
Explanation

grep ^ will match all lines in a file
grep -n will prefix each line of output with the line number within its input file

## Limitations:
Limitations
In some systems you might have to use egrep instead of grep.

