# lockntross

## Command:
```
$ docker ps -qa | xargs docker inspect --format='{{.LogPath}}' | xargs sudo du -hl; sleep 1; printf "\r\n  echo '' > \$(docker inspect --format={{.LogPath}} container_name_or_id) \r\n*****COPY****ABOVE****TO******CLEAR*****LOG*****CHANGE***CONTAINER_ID******* \r\n \n"
```

## Explanation:
No explanation available

## Limitations:
No limitations specified

