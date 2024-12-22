# Redirection operator to override the noclobber option

## Command:
```
$ some_command >| output.txt
```

## Explanation:
Explanation
Normally the > operator overwrites the target file.
If the noclobber option is set (using: set -o noclobber), the > operator will fail if the target file exists.
The >| overrides the noclobber setting and overwrites the target file.
If the noclobber option is not set, then >| is equivalent to >, naturally.

## Limitations:
No limitations specified

