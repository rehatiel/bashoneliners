# Recording SSH sessions

## Command:
```
$ ssh -l USER HOST | tee -a /path/to/file
```

## Explanation:
Explanation
tee is a command which displays or pipes the output of a command and copies it into a file or a variable.
The -a option appends the output to the end of file instead of writing over it.
You can also create an alias in ~/.bashrc to record your session when using ssh:
function sshlog () { \ssh $@ 2>&1 | tee -a $(date +%Y%m%d).log; }
alias ssh=sshlog

## Limitations:
No limitations specified

