# Print wifi access points sorted by signal

## Command:
```
$ iw dev IFACE scan | egrep "SSID|signal" | awk -F ":" '{print $2}' | sed 'N;s/\n/:/' | sort
```

## Explanation:
Explanation

iw dev IFACE scan get info about scanned APs
egrep "SSID|signal" take only name and signal
awk -F ":" '{print $2}' cut labels of fields
sed 'N;s/\n/:/' join couples to single line
sort sort by signal asc

IFACE - wifi interface (like wlan0)

## Limitations:
No limitations specified

