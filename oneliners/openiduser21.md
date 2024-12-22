# openiduser21

## Command:
```
$ find /etc -type f -print0 2>/dev/null | xargs -0 grep --color=AUTO -Hn 'nameserver' 2>/dev/null
```

## Explanation:
Explanation
In the example above, find and display every file in /etc containing the string nameserver with the corresponding line, including line number, sample output:

/etc/ppp/ip-up.d/0dns-up:9:# Rev. Dec 22 1999 to put dynamic nameservers last.
/etc/ppp/ip-up.d/0dns-up:23:# nameservers given by the administrator.  Those for which 'Dynamic' was chosen
/etc/ppp/ip-up.d/0dns-up:24:# are empty.  0dns-up fills in the nameservers when pppd gets them from the
/etc/ppp/ip-up.d/0dns-up:26:# 'search' or 'domain' directives or additional nameservers.  Read the 
/etc/ppp/ip-up.d/0dns-up:77:# nameserver lines to the temp file.

## Limitations:
Limitations

-i use for case insensitive search;

