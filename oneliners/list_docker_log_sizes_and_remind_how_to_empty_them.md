# list docker log sizes and remind how to empty them

## Command:
```
$ docker ps -qa | xargs docker inspect --format='{{.LogPath}}' | xargs sudo du -hl; sleep 1; printf "\r\n  echo '' > \$(docker inspect --format={{.LogPath}} container_name_or_id) \r\n*****COPY****ABOVE****TO******CLEAR*****LOG*****CHANGE***CONTAINER_ID******* \r\n \n"
```

## Explanation:
Explanation
list docker log sizes in human readable format and print a reminder on how to empty them while they are running.

## Limitations:
No limitations specified

