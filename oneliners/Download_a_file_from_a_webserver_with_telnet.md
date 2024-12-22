# Download a file from a webserver with telnet

## Command:
```
$ (echo 'GET /'; echo; sleep 1; ) | telnet www.google.com 80
```

## Explanation:
Explanation
If you are ever in a minimal headless *nix which doesn't have any command line utilities for downloading files (no curl, wget, lynx) but you have telnet, then this can be a workaround.
Another option is netcat:
/usr/bin/printf 'GET / \n' | nc www.google.com 80

Credit goes to this post:
http://unix.stackexchange.com/a/83987/17433

## Limitations:
No limitations specified

