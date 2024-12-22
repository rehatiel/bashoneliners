# Test your hard drive speed

## Command:
```
$ time (dd if=/dev/zero of=zerofile bs=1M count=500;sync);rm zerofile
```

## Explanation:
Explanation
Creates a 500MB blank file and times how long it takes to finish writing the entire thing to disk (sync)
time the entire dd + sync operation, and then remove the temporary file

## Limitations:
Limitations
Works with Bash; not tested in other environments

