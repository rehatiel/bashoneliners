# Rename all files in a directory to lowercase names

## Command:
```
$ paste <(ls) <(ls | tr A-Z a-z) | while read OLD NEW; do echo mv -v $OLD $NEW; done
```

## Explanation:
Explanation

<(cmd) is the filename of a named pipe (FIFO), where the named pipe is filled by the output of cmd
paste puts together the named pipes to form two columns: first column with the original filenames, second column with the lowercased filenames
... | tr abc ABC transforms stdin by replacing any characters that appear in the first set of letters to the second set of letters
while read old new; do ...; done for each line it reads the first column into $old and the second column into $new

## Limitations:
Limitations

Won't work if there are spaces in a filename.

