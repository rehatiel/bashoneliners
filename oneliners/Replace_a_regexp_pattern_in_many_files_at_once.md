# Replace a regexp pattern in many files at once

## Command:
```
$ vi +'bufdo %s/pattern/replacement/g | update' +q $(grep -rl pattern /path/to/dir)
```

## Explanation:
Explanation

The inner grep will search recursively in specified directory and print the filenames that contain the pattern.
All files will be opened in vi, one buffer per file.
The arguments starting with + will be executed as vi commands:
bufdo %s/pattern/replacement/g | update = perform the pattern substitution in all files and save the changes
q = exit vi

## Limitations:
Limitations
The :bufdo command might not be there in old versions of vim.

