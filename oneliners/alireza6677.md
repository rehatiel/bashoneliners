# alireza6677

## Command:
```
$ up(){ DEEP=$1; for i in $(seq 1 ${DEEP:-"1"}); do cd ../; done; }
```

## Explanation:
Explanation
Include this function in your .bashrc
Now you are able to go back in your path simply with up N. So, for example:
Z:~$ cd /var/lib/apache2/fastcgi/dynamic/
Z:/var/lib/apache2/fastcgi/dynamic$ up 2
Z:/var/lib/apache2$ up 3
Z:/$

## Limitations:
No limitations specified

