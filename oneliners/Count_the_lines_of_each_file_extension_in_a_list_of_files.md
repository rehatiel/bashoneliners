# Count the lines of each file extension in a list of files

## Command:
```
$ git ls-files | xargs wc -l | awk -F ' +|\\.|/' '{ sumlines[$NF] += $2 } END { for (ext in sumlines) print ext, sumlines[ext] }'
```

## Explanation:
Explanation
The pipeline:

git ls-files -- produces the list of files in a Git repository. It could be anything else that produces a list of filenames, for example: find . -type f
xargs wc -l -- run wc -l to count the lines in the filenames coming from standard input. The output is the line count and the filename
The final awk command does the main work: extract the extension name and sum the line counts:
-F ' +|\\.|/' -- use as field separator multiples of spaces, or a dot, or a slash
{ sumlines[$NF] += $2 } -- $NF contains the value of the last field, which is the filename extension, thanks to the dot in the field separator, and $2 contains the value of the second field in the input, which is the line count. As a result, we are building the sumlines associative array, summing up the line counts of files with the same extension
END { for (ext in sumlines) print ext, sumlines[ext] }' -- After all lines have been processed, print the extension and the line count.

## Limitations:
No limitations specified

