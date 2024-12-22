# Generate a random 32 characters password

## Command:
```
$ tr -dc 'a-zA-Z0-9~!@#$%^&*_()+}{?></";.,[]=-' < /dev/urandom | fold -w 32 | head -n 1
```

## Explanation:
Explanation
The tr command filters characters from /dev/urandom: it deletes characters that don't match what is specified in its argument (a-zA-Z0-9~!@#$%^&*_()+}{?></";.,[]=-).
Then the fold command wraps the output every 32 characters and head takes only the first line, effectively stopping the pipeline after 32 characters were printed.

## Limitations:
No limitations specified

