# Print the lines of file2 that are missing in file1

## Command:
```
$ grep -vxFf file1 file2
```

## Explanation:
Explanation

-f is to specify a file with the list of patterns: file1
-F is to treat the patterns fixed strings, without using regular expressions
-x is to match exactly the whole line
-v is to select non-matching lines

The result is effectively the same as:
diff file1 file2 | grep '^>' | sed -e s/..//

## Limitations:
Limitations
The flags of grep might work differently depending on the system. So yeah you might prefer the second way which should work everywhere. Nonetheless the various of flags of grep are interesting.

