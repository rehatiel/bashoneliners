# Anntoin

## Command:
```
$ find . -name 'filename' | xargs -r ls -tc | head -n1
```

## Explanation:
Explanation
Shows latest file (by last modification of file status information) for the given pattern. So in this example filename = custlist*.xls.
We use ls to do the sorting (-t) and head to pick the top one.
xargs is given the -r option so that ls isn't run if there is no match.

## Limitations:
Limitations
The filesystem needs to support ctime. Does not depend on a consistent naming scheme.

