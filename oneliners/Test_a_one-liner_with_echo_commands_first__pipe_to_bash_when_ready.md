# Test a one-liner with echo commands first, pipe to bash when ready

## Command:
```
$ paste <(ls) <(ls | tr A-Z a-z) | while read OLD NEW; do echo mv -v $OLD $NEW; done | sh
```

## Explanation:
Explanation
You can do a lot of damage with a single one-liner. So while testing the sequence and syntax of commands it's good to just echo the commands that you will want to execute in the end, rather than really executing them. If the output looks good, don't bother removing the echo-s (which can be error prone), it's easier and safer to just pipe the echoed commands to bash to execute.

## Limitations:
No limitations specified

