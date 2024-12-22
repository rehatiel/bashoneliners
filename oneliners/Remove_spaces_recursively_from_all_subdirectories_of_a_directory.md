# Remove spaces recursively from all subdirectories of a directory

## Command:
```
$ find /path/to/dir -type d | tac | while read LINE; do target=$(dirname "$LINE")/$(basename "$LINE" | tr -d ' '); echo mv "$LINE" "$target"; done
```

## Explanation:
Explanation

find path_to_dir -type d finds all the subdirectories
tac reverses the order. This is important to make "leaf" directories come first! 
target=... stuff constructs the new name, removing spaces from the leaf component and keeping everything before that the same
echo mv ... for safety you should run with "echo" first, if the output looks good then remove the "echo" to really perform the rename

## Limitations:
Limitations
In UNIX or BSD there is no tac. There you can use tail -r instead.

