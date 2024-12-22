# Find all the unique 4-letter words in a text

## Command:
```
$ cat ipsum.txt | perl -ne 'print map("$_\n", m/\w+/g);' | tr A-Z a-z | sort | uniq | awk 'length($1) == 4 {print}'
```

## Explanation:
Explanation

The perl regex pattern m/\w+/g will match consecutive non-word characters, resulting in a list of all the words in the source string
map("$_\n", @list) transforms a list, appending a new-line at the end of each element
tr A-Z a-z transforms uppercase letters to lowercase
In awk, length($1) == 4 {print} means: for lines matching the filter condition "length of the first column is 4", execute the block of code, in this case simply print

## Limitations:
No limitations specified

