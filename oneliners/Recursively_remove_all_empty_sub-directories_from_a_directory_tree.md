# Recursively remove all empty sub-directories from a directory tree

## Command:
```
$ find . -type d | tac | xargs rmdir 2>/dev/null
```

## Explanation:
Explanation

find will output all the directories
tac reverses the ordering of the lines, so "leaf" directories come first
The reordering is important, because rmdir removes only empty directories
We redirect error messages (about the non-empty directories) to /dev/null

## Limitations:
Limitations
In UNIX and BSD systems you might not have tac, you can try the less intuitive tail -r instead.

