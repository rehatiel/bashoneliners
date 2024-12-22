# Use rsync instead of cp to get a progress indicator when copying large files

## Command:
```
$ rsync --progress largefile.gz somewhere/else/
```

## Explanation:
Explanation
Although rsync is famous for synchronizing files across machines, it also works locally on the same machine. And although the cp command doesn't have progress indicator, which can be annoying when copying large files, but rsync does have it, so there you go.

## Limitations:
Limitations
When copying directories be careful that the meaning of a trailing slash when specifying directories can be slightly different from cp.

