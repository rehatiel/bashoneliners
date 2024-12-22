# spotmac

## Command:
```
$ netstat -rn | awk '/default/ { print $NF }' | head -1 | xargs -I {}  ifconfig {} | awk '/ether/ {print $2}'
```

## Explanation:
Explanation
netstat -rn -> get routing table
awk '/default/ { print $NF }' -> grep the default routes 
head -1 -> limit to the first result (is also the interface with the highest priority 
xargs -I {}  ifconfig {}  -> use the result to get data from ifconfig
awk '/ether/ {print $2}' ->grep the mac address.

## Limitations:
Limitations
Tested on OSX.

