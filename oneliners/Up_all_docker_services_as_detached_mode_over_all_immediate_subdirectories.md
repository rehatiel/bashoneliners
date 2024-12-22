# Up all docker services as detached mode over all immediate subdirectories

## Command:
```
$ for dir in $(ls -d */); do eval $(cd $PWD/$dir && docker-compose up -d && cd ..); done;
```

## Explanation:
Explanation
Supposing that you are in a directory that contains many subdirectories with a docker-compose file each one and instead of up one by one manually you want run all at time, well this is a helpful command for this purpose

## Limitations:
No limitations specified

