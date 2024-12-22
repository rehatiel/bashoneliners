# Do something in another directory without going there

## Command:
```
$ (cd /path/to/somewhere; tar c .) > somewhere.tar
```

## Explanation:
Explanation
As explained superbly in man bash:
   (list) list is executed in a subshell environment (see  COMMAND  EXECU-
          TION  ENVIRONMENT below).  Variable assignments and builtin com-
          mands that affect the  shell's  environment  do  not  remain  in
          effect  after  the  command completes.  The return status is the
          exit status of list.

In other words, this is a handy way to do something somewhere else without having to go there and coming back.

## Limitations:
No limitations specified

