# jasembo

## Command:
```
$ for i in $(echo -e 'G\nM\nK'); do du -hsx /* 2>/dev/null | grep '[0-9]'$i | sort -rn; done
```

## Explanation:
Explanation

echo -e prints G for Gigabytes, M for Megabytes and K for Kilobytes in a line each.
2>/dev/null send stderr to /dev/null
sort -rn sorts in reverse numerical order. Largest first

## Limitations:
No limitations specified

