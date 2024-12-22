# Find all of the distinct file extensions in a folder

## Command:
```
$ find . -type f | perl -ne 'print $1 if m/\.([^.\/]+)$/' | sort -u
```

## Explanation:
Explanation
Will find all of the distinct file extensions in a folder hierarchy.
Originally posted at: 
http://stackoverflow.com/questions/1842254/how-can-i-find-all-of-the-distinct-file-extensions-in-a-folder-hierarchy

## Limitations:
No limitations specified

