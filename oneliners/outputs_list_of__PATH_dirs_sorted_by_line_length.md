# outputs list of $PATH dirs sorted by line length

## Command:
```
$ echo -e ${PATH//:/\\n} | awk '{print length, $0}' | sort -n | cut -f2- -d' '
```

## Explanation:
Explanation
when it prints your path the output should look something like  ◣   
/bin    
/sbin   
/usr/bin    
/usr/sbin    
/opt/X11/bin    
/usr/libexec    
/opt/local/bin   
/usr/local/bin

## Limitations:
No limitations specified

