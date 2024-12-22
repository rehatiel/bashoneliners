# Remove offending key from known_hosts file with one swift move

## Command:
```
$ vi +18d +wq ~/.ssh/known_hosts
```

## Explanation:
Explanation
When you try to ssh to a server where the host key has changed then you probably get an error message like this:
Offending key in /home/jack/.ssh/known_hosts:18

If you know for sure that it was the server's admins who changed the host key, then your next move is to remove line 18 from the file so that ssh lets you connect after accepting the new key.
The one-liner does this in one swift move by passing simple commands to vi:

+18d -- delete line 18
+wq -- save the file and exit

## Limitations:
Limitations
This works as posted in GNU sed.
In BSD sed, the -i flag requires a parameter to use as the suffix of a backup file.
You can set it to empty to not use a backup file:
sed -i'' 18d .ssh/known_hosts

