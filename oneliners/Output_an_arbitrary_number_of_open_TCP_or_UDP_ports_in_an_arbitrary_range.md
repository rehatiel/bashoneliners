# Output an arbitrary number of open TCP or UDP ports in an arbitrary range

## Command:
```
$ comm -23 <(seq "$FROM" "$TO") <(ss -tan | awk '{print $4}' | cut -d':' -f2 | grep "[0-9]\{1,5\}" | sort | uniq) | shuf | head -n "$HOWMANY"
```

## Explanation:
Explanation
Originally published (by me) on unix.stackexchange.com.
comm is a utility that compares sorted lines in two files. It outputs three columns: lines that appear only in the first file, lines that only appear in the second one and common lines. By specifying -23 we suppress the latter columns and only keep the first one. We can use this to obtain the difference of two sets, expressed as a sequence of text lines. I learned about comm here.
The first file is the range of ports that we can select from. seq produces a sorted sequence of numbers from $FROM to $TO. The result is piped to comm as the first file using process substitution.
The second file is the sorted list of ports, that we obtain by calling the ss command (with -t meaning TCP ports, -a meaning all - established and listening - and -n numeric - don't try to resolve, say, 22 to ssh). We then pick only the fourth column with awk, which contains the local address and port. We use cut to split address and port with the : delimiter and keep only the latter (-f2). ss also output an header, that we get rid of by grepping for non-empty sequences of numbers that are no longer than 5. We then comply with comm's requirement by sorting numerically (-n) and getting rid of duplicates with uniq.
Now we have a sorted list of open ports, that we can shuffle to then grab the first "$HOWMANY" ones with head -n.
Example
Grab the three random open ports in the private range (49152-65535)
comm -23 <(seq 49152 65535) <(ss -tan | awk '{print $4}' | cut -d':' -f2 | grep "[0-9]\{1,5\}" | sort | uniq) | shuf | head -n 3

could return for example
54930
57937
51399

Notes

switch -t with -u in ss to get free UDP ports instead.
drop shuf if you're not interested in grabbing a random port

## Limitations:
No limitations specified

