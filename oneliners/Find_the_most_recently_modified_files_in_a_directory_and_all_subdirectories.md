# Find the most recently modified files in a directory and all subdirectories

## Command:
```
$ find /path/to/dir -type f -mtime -7 -print0 | xargs -0 ls -lt | head
```

## Explanation:
Explanation

find /path/to/dir -type f -mtime -7 -print0 prints all the files in the directory tree that have been modified within the last 7 days, with null character as the delimiter
xargs -0 ls -lt expects a null delimited list of filenames and will sort the files by modification time, in descending order from most recent to oldest
Since we are looking for the most recent files, with head we get the first 10 lines only

Note that if there are too many files in the output of find, xargs will run multiple ls -lt commands and the output will be incorrect. This is because the maximum command line length is getconf ARG_MAX and if this is exceeded xargs has to split the execution to multiple commands. So depending on your use case you may need to tweak the -mtime parameter to make sure there are not too many lines in the output.

## Limitations:
No limitations specified

