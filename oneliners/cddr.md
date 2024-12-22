# cddr

## Command:
```
$ ps -ef |awk '{ print $2 }' \ 	|tail -n +2 \ 	|while read pid; do echo "$pid	$(lsof -p $pid |wc -l)"; done \ 	|sort -r -n -k 2 \ 	|while read pid count; do echo "$pid	$count	$(ps -o command= -p $pid)"; done
```

## Explanation:
No explanation available

## Limitations:
No limitations specified

