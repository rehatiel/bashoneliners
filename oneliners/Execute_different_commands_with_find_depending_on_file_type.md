# Execute different commands with find depending on file type

## Command:
```
$ find /path/to/dir -type d -exec chmod 0755 '{}' \; -o -type f -exec chmod 0644 '{}' \;
```

## Explanation:
Explanation

-type d -exec chmod 0755 '{}' \; for each directory, run chmod 0755
\; is to mark the end of the -exec
{} is replaced with the filename, we enclosed it in single quotes like this '{}' to handle spaces in filenames
-ological OR operator
-type f -exec chmod 0644 '{}' \; for each regular file, run chmod 0644

## Limitations:
No limitations specified

