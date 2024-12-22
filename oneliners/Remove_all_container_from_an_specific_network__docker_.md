# Remove all container from an specific network (docker)

## Command:
```
$ docker ps -a -f network=$NETWORK --format='{{.ID}}' | xargs docker rm -f
```

## Explanation:
Explanation
docker ps -a -f network=$NETWORK --format='{{.ID}}' returns the id's of all container that are subscribed to the network and pass the output to xargs docker rm -f that stop and deletes each container

## Limitations:
No limitations specified

