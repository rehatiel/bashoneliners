# kazatca

## Command:
```
$ iw dev IFACE scan | egrep "SSID|signal" | awk -F ":" '{print $2}' | sed 'N;s/\n/:/' | sort
```

## Explanation:
No explanation available

## Limitations:
No limitations specified

