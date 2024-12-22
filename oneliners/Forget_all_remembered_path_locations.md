# Forget all remembered path locations

## Command:
```
$ hash -r
```

## Explanation:
Explanation
bash remembers the full path name of each command you enter, so it doesn't have to lookup in $PATH every single time you run the same thing. It also counts the number of times you used each command in the current session, you can see the list with hash.
Anyway, this behavior can poses a small problem when you reinstall an application at a different path. For example you reinstall a program that used to be in /usr/local/bin and now it is in /opt/local/bin. The problem is that if you used that command in the current shell session, then bash will remember the original location, which of course doesn't work anymore. To fix that, you can either run hash cmd which will lookup the command again, or run hash -r to forget all remembered locations (less efficient, but maybe faster to type ;-)
For more details, see help hash

## Limitations:
No limitations specified

