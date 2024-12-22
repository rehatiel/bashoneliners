# jam

## Command:
```
$ find . -type f -name '*.html' -exec sed -i -e '1r common_header' -e '1,/STRING/d' {} \;
```

## Explanation:
Explanation
Replaces the lines from 1 to the first occurrence of a line starting with STRING of every file found with find.

find . -type f -name '*.html' returns a list of all files (not including directories) ending with .html. The ' ' in name is used to pass the literal wildcard * to the find command, instead of the * interpretation of bash, that is, repeat the command for every file in the current folder.
-exec execute the following command in each of the files found, using {} as the filename. the ; termination must be escaped with \;
sed -i replaces in file (output is the same file)
-e '1r common_header' -e '1,/STRING/d' {} reads common_header file, then finds the first occurrence of STRING and replaces it, deleting all the previous lines and putting the contents of common_header.

## Limitations:
No limitations specified

