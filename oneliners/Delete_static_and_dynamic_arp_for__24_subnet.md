# Delete static and dynamic arp for /24 subnet

## Command:
```
$ for i in {1..254}; do arp -d 192.168.0.$i; done
```

## Explanation:
Explanation
Simply loop from 1 to 254 and run arp -d for each IP address in the 192.168.0.0/24 network.

## Limitations:
No limitations specified

