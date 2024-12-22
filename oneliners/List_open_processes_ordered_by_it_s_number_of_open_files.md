# List open processes ordered by it's number of open files

## Command:
```
$ ps -ef |awk '{ print $2 }' \ 	|tail -n +2 \ 	|while read pid; do echo "$pid	$(lsof -p $pid |wc -l)"; done \ 	|sort -r -n -k 2 \ 	|while read pid count; do echo "$pid	$count	$(ps -o command= -p $pid)"; done
```

## Explanation:
Explanation
Combines ps, lsof, and sort in the ways you might expect to produce the intended outcome.

## Limitations:
No limitations specified

