# Sort du output in Human-readable format

## Command:
```
$ for i in G M K; do du -hsx * | grep "[0-9]$i\b" | sort -nr; done 2>/dev/null
```

## Explanation:
Explanation

The reason to use a for loop is to sort results with G or M or K values separately, otherwise sort -n would just sort everything by the numbers regardless of G M K suffix.
grep "[0-9]$i\b" matches lines containing a digit followed by G or M or K followed by a "word boundary"

## Limitations:
Limitations
Probably a newer GNU only option for sort. :D

