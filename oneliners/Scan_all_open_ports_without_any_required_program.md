# Scan all open ports without any required program

## Command:
```
$ for i in {1..65535}; do (echo < /dev/tcp/127.0.0.1/$i) &>/dev/null && printf "\n[+] Open Port at\n: \t%d\n" "$i" || printf "."; done
```

## Explanation:
Explanation
You can scan ports of an IP without any required programs like nmap.

## Limitations:
Limitations
Tested on Linux, not sure it works on other OS.

