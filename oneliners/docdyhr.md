# docdyhr

## Command:
```
$ pip install -U $(pip list --outdated 2> /dev/null | grep -v 'Version' | grep -v '------' | awk '{printf $1 " " }' && echo)
```

## Explanation:
No explanation available

## Limitations:
No limitations specified

