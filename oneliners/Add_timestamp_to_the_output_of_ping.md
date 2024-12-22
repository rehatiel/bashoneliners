# Add timestamp to the output of ping

## Command:
```
$ ping some_host | while read LINE; do echo $(date): $LINE; done
```

## Explanation:
Explanation
The while loop reads the output of ping line by line, and echoes it back with $(date) prepended.

## Limitations:
No limitations specified

