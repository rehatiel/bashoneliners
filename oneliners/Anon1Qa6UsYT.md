# Anon1Qa6UsYT

## Command:
```
$ find /path/to/drive -type f -exec file -b '{}' \; -printf '%s\n' | awk -F , 'NR%2 {i=$1} NR%2==0 {a[i]+=$1} END {for (i in a) printf("%12u %s\n",a[i],i)}' | sort -nr
```

## Explanation:
Explanation
versorge asks:

I have a bunch of usb volumes lying around and I would like to get a quick summary of what is on the drives. How much space is taken up by pdf, image, text or executable files. This could be output as a text summary, or a pie chart.

This one-liner produces a list like this:
  5804731229 FLAC audio bitstream data
   687302212 MPEG sequence
    99487460 data
    60734903 PDF document
    55905813 Zip archive data
    38430192 ASCII text
    32892213 gzip compressed data
    24847604 PNG image data
    16618355 XML 1.0 document text
    13876248 JPEG image data

The find command locates all regular files (-type f) below the given directory, which could be a mounted USB stick or any other directory.  For each one, it runs the file -b command with the filename to print the file type; if this succeeds, it also prints the file size (-printf '%s\n').  This results in a list containing a file type on one line, followed by the file size on the next.
The awk script takes this as input.  The GNU file command often produces very specific descriptions such as GIF image data, version 87a, 640 x 480 - to generalize these, we set the field separator to be a comma with the -F option.  Referencing $1 then only uses what's to the left of the first comma, giving us a more generic description like GIF image data.
In the awk script, the first pattern-action pair NR%2 {i=$1} applies to each odd-numbered line, setting the variable i to be the file type description.  The even-numbered lines are handled by NR%2==0 {a[i]+=$1}, adding the value of the line (which is the file size) to the array variable a[i].  This results in an array indexed by file type, with each array member holding the cumulative sum of bytes for that type.  The END { ... } pattern-action pair finally prints out a formatted list of the total size for each file type.
At the end of the line, the sort command sorts the list, putting the file types with the largest numbers at the top.

## Limitations:
Limitations
This one-liner uses the -b option to file and the -printf primary of find - these are supported by the GNU utilities but may not work elsewhere.  It can also take a long time to run, since it needs to open and analyze every file below the given directory.

