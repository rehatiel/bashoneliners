# Check the performance of a script by re-running many times while measuring the running time

## Command:
```
$ for i in {1..10}; do time curl http://localhost:8000 >/dev/null; done 2>&1 | grep real
```

## Explanation:
Explanation

{1..10} creates a sequence from 1 to 10, for running the main script 10 times
2>&1 redirects stderr to stdout, this is necessary to capture the "output" of the time builtin

## Limitations:
No limitations specified

