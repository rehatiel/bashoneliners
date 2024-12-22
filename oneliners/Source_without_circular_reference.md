# Source without circular reference

## Command:
```
$ [ ! "${LIB}" ] && ( readonly LIB; . "${ $( cd $( dirname $0 ) && pwd ) }/<path_to>/LIB.sh" )
```

## Explanation:
Explanation
Source LIB only if the corresponding variable is not defined, in order to prevent circular reference loop in case of the same script has been sourced before during the sourcing event.

## Limitations:
No limitations specified

