# Find files that are not executable

## Command:
```
$ find /some/path -type f ! -perm -111 -ls
```

## Explanation:
Explanation
The key is writing the parameter of -perm correctly. The value -111 means that all execution bits must be set: user and group and other too. By negating this pattern with ! we get files that miss any of the execution bits.
If you want to be more specific, for example find files that are not executable specifically by the owner, you could do like this:
find /some/path -type f ! -perm -100 -ls

The -ls option is to print the found files using a long listing format similar to the ls command.

## Limitations:
No limitations specified

