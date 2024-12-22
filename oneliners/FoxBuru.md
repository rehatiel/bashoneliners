# FoxBuru

## Command:
```
$ sudo journalctl -b | grep -o "PROTO=.*" | sed -r 's/(PROTO|SPT|DPT|LEN)=//g' | awk '{print $1, $3}' | sort | uniq -c
```

## Explanation:
Explanation
We take the output of journalctl since the last boot (-b flag) and output from PROTO= until the EOL. Then, we remove identification tags (PROTO=/SPT=/DPT=/LEN=) and print just the protocol and destination port (cols 1 and 3). We sort the output properly so we can aggregate them on the call over uniq.

## Limitations:
Limitations

Only works on Linux
You use firewalld and you have logging set on ALL
(see firewalld.conf for details)
You use journald for logging
Your user has sudo privileges

