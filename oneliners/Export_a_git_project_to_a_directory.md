# Export a git project to a directory

## Command:
```
$ git archive master | tar x -C /path/to/dir/to/export
```

## Explanation:
Explanation
The git archive command basically creates a tar file. The one-liner is to create a directory instead, without an intermediate tar file. 
The tar command above will untar the output of git archive into the directory specified with the -C flag. The directory must exist before you run this command.

## Limitations:
No limitations specified

