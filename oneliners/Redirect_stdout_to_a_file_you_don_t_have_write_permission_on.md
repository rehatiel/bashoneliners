# Redirect stdout to a file you don't have write permission on

## Command:
```
$ echo hello | sudo tee -a /path/to/file
```

## Explanation:
Explanation

The tee command copies standard input to standard output, making a copy in zero or more files.
If the -a flag is specified it appends instead of overwriting.
Calling tee with sudo makes it possible to write to files the current user has no permission to but root does.

## Limitations:
No limitations specified

