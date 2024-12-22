# report disk usage by file type

## Command:
```
$ find . -type f -empty -prune -o -type f -printf "%s\t" -exec file --brief --mime-type '{}' \; | awk 'BEGIN {printf("%12s\t%12s\n","bytes","type")} {type=$2; a[type]+=$1} END {for (i in a) printf("%12u\t%12s\n", a[i], i)|"sort -nr"}'
```

## Explanation:
Explanation
find . look in current directory
-type f -empty -prune -o -type f all non-empty files
-printf "%s\t" -exec file --brief --mime-type '{}' \; print file size, [tab], and run the file command to get mime-type;
| awk 'BEGIN {printf("%12s\t%12s\n","bytes","type")}  pipe to awk, print column headers,
{type=$2; a[type]+=$1} build a dictionary of mime-types, increment value by file size. this creates a running total of size per file-type.
END {for (i in a) printf("%12u\t%12s\n", a[i], i) |"sort -nr"}' print the result, sorted
example output
       bytes            type
    10422306    application/x-gettext-translation
     6759737      text/plain
     6653499      text/x-php
     2316621    application/octet-stream
     1486637       text/html
      714594    application/zlib
      524756       image/png
      210196    text/x-pascal
       45489      text/x-asm

## Limitations:
Limitations
This one-liner uses the -b option to file and the -printf primary of find - these are supported by the GNU utilities but may not work elsewhere.  It can also take a long time to run, since it needs to open and analyze every file below the given directory.

