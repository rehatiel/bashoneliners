# Print file owners and permissions of a directory tree

## Command:
```
$ find /path/to/dir1 -printf "%U %G %m %p\n" > /tmp/dir1.txt
```

## Explanation:
Explanation
The command simply traverses the specified directory tree and for each file and directory it prints the UID of the owner, GID of the group, the permission bits and the path. 
To compare file owners and permissions of two directory trees you can run this command for each directory, save the output in two files and then compare them using diff or similar.
See man find for more explanation of all the possible symbols you can use with -printf

## Limitations:
Limitations
The -printf option does not exist in find on Solaris 10.

