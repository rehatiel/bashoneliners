# Print the lines of file2 that are missing in file1

## Command:
```
$ comm -23 file2 file1
```

## Explanation:
Explanation
The POSIX-standard comm utility can do this also.

-2 suppresses lines from the second argument (file1)
-3 suppresses lines appearing in both files

## Limitations:
Limitations
Assumes that file1 and file2 are already sorted.  If they are not, you can use process substitution to do so:
comm -23 <(sort file2) <(sort file1)
Process substitution is a bash-specific feature (also available in zsh but with a different syntax).

