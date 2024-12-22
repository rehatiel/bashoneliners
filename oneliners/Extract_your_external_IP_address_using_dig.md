# Extract your external IP address using dig

## Command:
```
$ dig +short myip.opendns.com @resolver1.opendns.com
```

## Explanation:
Explanation
This asks the IP address of myip.opendns.com from the name server resolver1.opendns.com (something you trust), which will return your external IP address.
If you don't have dig, you could use these other services instead:
curl ipecho.net/plain
curl icanhazip.com
curl curlmyip.com
curl l2.io/ip
curl ip.appspot.com
curl ifconfig.me/ip

## Limitations:
Limitations
All these methods rely on external services, which might be sometimes temporarily or even permanently down. In that case, find an alternative service.

