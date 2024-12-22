# openiduser93

## Command:
```
$ find . -maxdepth 1 -type f -name '\.*' | sed -e 's,^\./\.,,' | sort | xargs -iname mv .name name
```

## Explanation:
Explanation
This will remove the leading dot from all files in the current directory using mv, effectively "unhiding" them.
It will not affect subdirectories.

## Limitations:
Limitations
Probably only works on GNU Linux, due to the specific usage of xargs.

