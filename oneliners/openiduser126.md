# openiduser126

## Command:
```
$ ssh-keygen -R <hostname>
```

## Explanation:
Explanation
The ssh-keygen tool comes with an option for this already, there is no need for esoteric one-liners that are hard to remember.
Say you ssh server.example.com and its host key has changed because you just reinstalled it. Run ssh-keygen -R server.example.com then try to connect to the server again, you'll be presented with the option to save the host key just like new.

## Limitations:
Limitations
This works as posted in GNU sed.
In BSD sed, the -i flag requires a parameter to use as the suffix of a backup file.
You can set it to empty to not use a backup file:
sed -i'' 18d .ssh/known_hosts

