# n00tz

## Command:
```
$ find . -name *conf* -exec grep -Hni 'matching_text' {} \; > matching_text.conf.list
```

## Explanation:
Explanation
find . -name *conf*
In current directory, recursively find all files with 'conf' in the filename.
-exec grep -Hni 'matching_text' {} \; When a file is found matching the find above, execute the grep command to find all lines within the file containing 'matching_text'.

Here are what each of the grep switches do:
grep -i ignore case.
grep -H print the filename
grep -n print the line number

> matching_text.conf.list Direct the grep output to a text file named 'matching_text.conf.list'

## Limitations:
No limitations specified

