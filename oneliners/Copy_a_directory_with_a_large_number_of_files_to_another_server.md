# Copy a directory with a large number of files to another server

## Command:
```
$ tar cp -C /path/to/dir . | ssh server2 'tar x -C /path/to/target'
```

## Explanation:
Explanation
With a large number of files, scp or rsync can take very very long. It's much faster to tar up on one side and extract on the other. Without the -f flag tar writes output to standard output and expects input from standard input, so piping to ssh can work this way, without creating any intermediary files.
You may (or may not) gain an extra speed boost by compression, either with the z flag for tar, or with the -C flag for ssh, or with gzip pipes in the middle, like this:

tar cp -C /path/to/dir . | gzip | ssh server2 'gzip -cd | tar x -C /path/to/target'

## Limitations:
Limitations
Depending on your system and version of tar, you may need to hyphenate the flags, for example tar -cp, and tar -x. The -C flag might also not work, but that shouldn't be too difficult to work around.

