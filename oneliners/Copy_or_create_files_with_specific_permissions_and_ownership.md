# Copy or create files with specific permissions and ownership

## Command:
```
$ install -b -m 600 /dev/null NEWFILE
```

## Explanation:
Explanation
This example creates a new (empty) file with permissions 600. You could also specify the owner and group using the -o and -g flags respectively.
Although you could accomplish the same for example by creating the file with touch and then change permissions with chmod and chown, or use umask to control the permissions of newly created files, those methods take multiple steps, while with install it is a single step.
You can also use install to copy multiple files to a directory with specified permissions like this:
install -m 600 -o jack -g wheel file1 file2 /path/to/existing/dir

## Limitations:
No limitations specified

