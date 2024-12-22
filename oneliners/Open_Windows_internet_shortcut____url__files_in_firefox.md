# Open Windows internet shortcut (*.url) files in firefox

## Command:
```
$ firefox $(grep -i ^url='*' file.url | cut -b 5-)
```

## Explanation:
Explanation
Extract urls from a *.url file and open in Firefox. (Note that *.url files in Windows are basically just text files, so they can be parsed with a few commands.)

grep extracts lines starting with url=
The -i flag is to ignore case
cut extracts the range of characters from the 5th until the end of lines
The output of $(...) will be used as command line parameters for Firefox

## Limitations:
Limitations
This only works with URLs that don't contain special characters that would be interpreted by the shell, such as spaces and others.

