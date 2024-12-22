# Using tcpdump with port ranges and file count/size

## Command:
```
$ sudo /usr/sbin/tcpdump -i any -s 0 -n -Z <user_name> -C 500 -W 100 -w /home/<user_name>/$(hostname).pcap -f '(port (# or # or # or # or # or # or ...) or portrange <start>-<end>)' &>/dev/null
```

## Explanation:
Explanation
Flags used here:

-i = Interface
-s = Snapshot length (default 262144)
-n = Don't convert addresses (i.e., host addresses, port numbers, etc.) to names.
-Z = User
-C = File size
-W = File count
-w = File name

## Limitations:
No limitations specified

