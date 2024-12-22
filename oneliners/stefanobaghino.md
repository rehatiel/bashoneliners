# stefanobaghino

## Command:
```
$ docker rmi $(docker images -f "dangling=true" -q)
```

## Explanation:
Explanation
docker images outputs all images currently available. By specifying -f "dangling=true" we restrict the list to "dangling" images (i.e. untagged). By specifying the -q option we use quiet mode, which limits the output to the images hash, which is the directly fed into docker rmi, which removes the images with the corresponding hashes.

## Limitations:
Limitations
This only works in the GNU version of xargs (thanks to the --no-run-if-empty), BSD does not have an equivalent that I know about.

