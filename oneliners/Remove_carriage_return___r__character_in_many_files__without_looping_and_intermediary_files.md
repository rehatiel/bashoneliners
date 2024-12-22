# Remove carriage return '\r' character in many files, without looping and intermediary files

## Command:
```
$ vi +'bufdo set ff=unix' +'bufdo %s/^M$//' +q file1 file2 file3
```

## Explanation:
Explanation

The arguments starting with + are commands in vi that will be executed
set ff=unix is a shortcut for set fileformat=unix and means to use "unix" file format, i.e. without the carriage return \r character. 
%s/^M$// is a pattern substitution for all lines in the entire buffer, the pattern is "carriage return at end of the line", where ^M is not two literal characters but actually one, to enter it on the command line press Ctrl followed by Enter/Return
bufdo means to run command in all buffers (each file is opened in a separate buffer)
q is to quit vi

Note: the set ff=unix is necessary, otherwise the pattern substitution will not do anything if all the lines end with \r = the file is in dos format, because in that case the line ending character will not be considered as part of the line.
Note: if a shell-script has "accidentally" some carriage returns in it, then when you try to execute you may get an error: bad interpreter: No such file or directory. This one-liner fixes that problem. If you know that all the lines in the file have the carriage return, and there is only one file to fix, then a simplified version of the one-liner is enough:
vi +'set ff=unix' +wq file1

## Limitations:
No limitations specified

