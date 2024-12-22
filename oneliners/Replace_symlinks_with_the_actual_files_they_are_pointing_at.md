# Replace symlinks with the actual files they are pointing at

## Command:
```
$ find /path/to/dir -type l -exec sh -c 'cp --remove-destination "$(readlink "{}")" "{}"' \;
```

## Explanation:
Explanation

All the double quoting is necessary to handle filenames with spaces.
Calling sh with -exec is necessary to evaluate readlink for each symlink

## Limitations:
Limitations
The BSD implementation of cp does not have the --remove-destination flag.

