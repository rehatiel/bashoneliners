# Kifli88

## Command:
```
$ for FILE in *.full ; do split -l 100000 $FILE; mv -f xaa `echo "$FILE" | cut -d'.' -f1`.txt; rm -f x*; done
```

## Explanation:
No explanation available

## Limitations:
No limitations specified

