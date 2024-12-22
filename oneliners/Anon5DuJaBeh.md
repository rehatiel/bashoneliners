# Anon5DuJaBeh

## Command:
```
$ sed -n '\@interface Ethernet3/1@,/!/ s/ip address/&/p' file...
```

## Explanation:
Explanation
Should have realized this can be done with sed, too - it's even shorter!
-n suppresses the normal printing of lines.
\@interface Ethernet3/1@,/!/ specifies the beginning and end of the stanza we want to work on, and addresses all lines in between.  Because the string we want to match at the beginning contains a slash, we need to designate a different character as the delimiter for the regular expression (@ in this case - note the backslash before the first one).  We are OK using slashes for the ending regex, which matches an exclamation mark.
While in the stanza of interest, we slightly abuse the s function with s/ip address/&/p.  This matches the text "ip address" and replaces it with... exactly the same thing (& just represents the matched text).  The reason we bother doing this is to take advantage of the p flag, which will print any line where a replacement has been made.
The result is that only lines which match "ip address" will be printed, and only when we are in the stanza of interest.

## Limitations:
Limitations
sed is a little less flexible - it uses basic regular expressions while awk uses extended regular expressions.  In addition, awk has a fuller set of functions and operators available, which can be used to create a wider variety of tests and actions.

