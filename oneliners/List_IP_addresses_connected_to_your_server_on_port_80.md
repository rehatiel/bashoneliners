# List IP addresses connected to your server on port 80

## Command:
```
$ netstat -tn 2>/dev/null | grep :80 | awk '{print $5}' | cut -d: -f1 | sort | uniq -c | sort -nr | head
```

## Explanation:
Explanation
This command is useful to detect when your server is under attack, and block those IPs.
Output:
 97 114.198.236.100
 56 67.166.157.194
 44 170.248.43.76
 38 141.0.9.20
 37 49.248.0.2
 37 153.100.131.12
 31 223.62.169.73
 30 65.248.100.253
 29 203.112.82.128
 29 182.19.66.187

Source:
https://www.mkyong.com/linux/list-all-ip-addresses-connected-to-your-server/

## Limitations:
No limitations specified

