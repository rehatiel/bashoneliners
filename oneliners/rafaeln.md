# rafaeln

## Command:
```
$ find . -type f -iname '*.un~' | while read UNDOFILE ; do FILE=$( echo "$UNDOFILE" | sed -r -e 's/.un~$//' -e 's&/\.([^/]*)&/\1&' ) ; [[ -e "$FILE" ]] || rm "$UNDOFILE" ; done
```

## Explanation:
Explanation
find -type f -iname '*.un~' finds every vim undo file and outputs the path to each on a separate line. At the beginning of the while loop, each of these lines is assigned in to the variable $UNDOFILE with while read UNDOFILE, and in the body of the while loop, the file each undo-file should be tracking is calculated and assigned to $FILE with FILE=$( echo "$UNDOFILE" | sed -r -e 's/.un~$//' -e 's&/\.([^/]*)&/\1&' ). If $FILE doesn't exist [[ -e "$FILE" ]] the undo-file is removed rm "$UNDOFILE".

## Limitations:
Limitations
I'm not sure whether sed in every flavour of UNIX allows the -r flag. That flag can be removed, though, as long as the parentheses in -e 's&/\.([^/]*)&/\1&' are escaped (but I think the way it stands the one-liner is more readable).

