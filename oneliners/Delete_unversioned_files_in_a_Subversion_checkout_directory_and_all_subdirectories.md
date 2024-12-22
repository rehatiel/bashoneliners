# Delete unversioned files in a Subversion checkout directory and all subdirectories

## Command:
```
$ svn st | grep ^? | sed -e 's/^? *//' | xargs -i{} echo rm -fr "{}"
```

## Explanation:
Explanation
If there are no spaces in the file names, a simpler command will be enough. This one-liner works even if there are spaces and certain special characters in the file names.

svn st shows the changes in the Subversion checkout
| grep ^? matches only lines starting with question mark (= unversioned files)
| sed -e 's/^? *//' removes the question mark at the beginning of the line and the space characters following it
| xargs -i{} echo rm -fr "{}" executes an echo command for each line in the input, where the command is formed by inserting the input line in the {} placeholder. Confirm the result looks good and remove the echo to perform the rm.

## Limitations:
Limitations
The command will not work with files that have " (double quote) in the name...

