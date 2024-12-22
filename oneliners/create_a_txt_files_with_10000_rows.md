# create a txt files with 10000 rows

## Command:
```
$ for FILE in *.full ; do split -l 100000 $FILE; mv -f xaa `echo "$FILE" | cut -d'.' -f1`.txt; rm -f x*; done
```

## Explanation:
Explanation
for loop will go trough every file that is finished with ".full" split that in file in files of 100000 rows. Rename the first one as input name but deleting the extension and adding ".txt" as extension. As last stem it will delete the rest of split files.

## Limitations:
No limitations specified

