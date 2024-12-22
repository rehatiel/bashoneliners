# Create a heap dump of a Java process

## Command:
```
$ jmap -dump:format=b,file=/var/tmp/dump.hprof 1234
```

## Explanation:
Explanation

Create a heap dump from the running Java process with PID=1234
The heap dump will be saved in /var/tmp/dump.hprof in binary format
You can open the dump with "MAT", the Memory Analyzer Tool (based on Eclipse) and identify objects that use most of the memory and potential memory leaks

For more options see jmap -h

## Limitations:
No limitations specified

