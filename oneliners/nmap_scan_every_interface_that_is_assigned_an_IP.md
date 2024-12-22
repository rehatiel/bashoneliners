# nmap scan every interface that is assigned an IP

## Command:
```
$ ifconfig -a | grep -Po '\b(?!255)(?:\d{1,3}\.){3}(?!255)\d{1,3}\b' | xargs nmap -A -p0-
```

## Explanation:
Explanation
ifconfig -a to output all interfaces, | grep -Po '\b(?!255)(?:\d{1,3}\.){3}(?!255)\d{1,3}\b' will search for 4 octets with up to three digits each, ignoring any leading or trailing 255. For my personal, and likely most local networks, this will exclude broadcast and netmask addresses without affecting host IPs. At this point, stdout holds any IP assigned to an interface, and will finally pipe to xargs, which supplies the IPs as arguments for nmap. Nmap then performs an OS detection, version detection, script, and traceroute scan on all 65536 ports of each assigned IP. 
Note: When using grep, -P is requrired to be able to interpret negative lookahead (?!) and non-capturing group (?:) brackets.

## Limitations:
Limitations
The regex epression will find both valid and non-valid IP addresses, e.g. 999.999.999.999, however invalid IPs are not an expected result of ifconfig -a. It is possible to correct this with a much longer regex expression, but not necessary in this case.

