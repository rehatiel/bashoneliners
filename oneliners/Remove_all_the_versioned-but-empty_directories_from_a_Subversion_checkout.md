# Remove all the versioned-but-empty directories from a Subversion checkout

## Command:
```
$ find . -name .svn -type d | while read ss; do dir=$(dirname "$ss"); test $(ls -a "$dir" | wc -l) == 3 && echo "svn rm \"$dir\""; done
```

## Explanation:
Explanation
Empty directories in version control stink. Most probably they shouldn't be there. Such directories have a single subdirectory in them named ".svn", and no other files or subdirectories.

The "find" searches for files files named .svn that are directories
The "while" assigns each line in the input to the variable ss
The "dirname" gets the parent directory of a path, the quotes are necessary for paths with spaces
ls -a should output 3 lines if the directory is in fact empty: ".", "..", and ".svn"
If the test is true and there are precisely 3 files in the directory, echo what we want to do
If the output of the one-liner looks good, pipe it to | sh to really execute

## Limitations:
No limitations specified

