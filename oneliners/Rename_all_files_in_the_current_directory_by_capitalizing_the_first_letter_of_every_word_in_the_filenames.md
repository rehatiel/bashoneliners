# Rename all files in the current directory by capitalizing the first letter of every word in the filenames

## Command:
```
$ ls | perl -ne 'chomp; $f=$_; tr/A-Z/a-z/; s/(?<![.'"'"'])\b\w/\u$&/g; print qq{mv "$f" "$_"\n}'
```

## Explanation:
Explanation

When you pipe something to perl -ne, each input line is substituted into the $_ variable. The chomp, tr///, s/// perl functions in the above command all operate on the $_ variable by default.
The tr/A-Z/a-z/ will convert all letters to lowercase.
The regular expression pattern (?<![.'])\b\w matches any word character that follows a non-word character except a dot or a single quote. 
The messy-looking '"'"' in the middle of the regex pattern is not a typo, but necessary for inserting a single quote into the pattern. (The first single quote closes the single quote that started the perl command, followed by a single quote enclosed within double quotes, followed by another single quote to continue the perl command.) We could have used double quotes to enclose the perl command, but then we would have to escape all the dollar signs which would make everything less readable.
In the replacement string $& is the letter that was matched, and by putting \u in front it will be converted to uppercase.
qq{} in perl works like double quotes, and can make things easier to read, like in this case above when we want to include double quotes within the string to be quoted.
After the conversions we print a correctly escaped mv command. Pipe this to bash to really execute the rename with | sh.

## Limitations:
Limitations
The above command will not work for files with double quotes in the name, and possibly other corner cases.

