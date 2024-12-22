# Print the first instance of $foo that occurs after $bar

## Command:
```
$ awk '/interface Ethernet3\/1/ {instanza=1} /!/ {instanza=0} instanza && /ip address/ {print}' file...
```

## Explanation:
Explanation
This can easily be done by setting a variable once the lead line of the stanza is found.  Take the following file as input:
interface Ethernet3/1
 ip address 172.30.10.2 255.255.0.0
 ip router isis area1
 no ip route-cache
 isis metric 10
!
interface Ethernet3/2
 ip address 192.168.10.10 255.255.255.0
 ip router isis area1
 no ip route-cache
 isis metric 10

The first awk pattern-action pair in the one-liner /interface Ethernet3\/1/ {instanza=1} sets the instanza variable to 1 (true) when it encounters the "interface Ethernet 3/1" line.  The second pattern-action /!/ {instanza=0} resets instanza back to 0 (false) once an exclamation point is encountered, ending the desired stanza.  The third pattern-action instanza && /ip address/ {print} prints any line containing "ip address," but only if we are still in the desired stanza (instanza is true): in this case, ip address 172.30.10.2 255.255.0.0.
If you only wanted to see the first matching line of the first matching stanza, you could change the third action to be {print; exit} and awk would quit after printing the first match.

## Limitations:
Limitations
sed is a little less flexible - it uses basic regular expressions while awk uses extended regular expressions.  In addition, awk has a fuller set of functions and operators available, which can be used to create a wider variety of tests and actions.

