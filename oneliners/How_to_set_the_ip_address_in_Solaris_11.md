# How to set the ip address in Solaris 11

## Command:
```
$ ipadm create-addr -T static -a 192.168.1.10/24 eth0/staticaddr
```

## Explanation:
Explanation

eth0 is the name of the network interface
ipadm show-if shows the list of network interfaces
staticaddr is a name you can choose

More details here: http://docs.oracle.com/cd/E19963-01/html/821-1458/gjwiq.html

## Limitations:
No limitations specified

