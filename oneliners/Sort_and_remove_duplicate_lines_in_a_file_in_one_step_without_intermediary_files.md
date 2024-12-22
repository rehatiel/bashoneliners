# Sort and remove duplicate lines in a file in one step without intermediary files

## Command:
```
$ vi +'%!sort | uniq' +wq file.txt
```

## Explanation:
Explanation
We open a file with vi and run two vi commands (specified with +):

%!sort | uniq
% = range definition, it means all the lines in the current buffer. 
! = run filter for the range specified. Filter is an external program, in this example sort | uniq


wq = write buffer contents to file and exit.

## Limitations:
No limitations specified

