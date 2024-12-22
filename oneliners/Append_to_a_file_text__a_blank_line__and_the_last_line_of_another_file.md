# Append to a file text, a blank line, and the last line of another file

## Command:
```
$ echo -e "From: me\n\n$(tail -n1 /var/log/apache2/error.log)" >> file
```

## Explanation:
Explanation

-e option to echo makes it interpret '\n' as a newline
$(command) syntax runs a command, then uses its output in place

## Limitations:
Limitations
The -e flag of echo doesn't work on all systems.
In that case you can use printf instead.

