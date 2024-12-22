# azat

## Command:
```
$ i=$(curl -s server/nginx_stats); IFS=$'\n'; i=($i); a=${i[0]/Active connections: } && a=${a/ }; r=${i[2]# [0-9]* [0-9]* }; echo "Active: $a, requests: $r"
```

## Explanation:
Explanation

Firstly download nginx statistics
IFS - set separator to new line only
i=$(i) # convert to *array*
a= # get active connections
r= # get requests

## Limitations:
No limitations specified

