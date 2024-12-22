# ManuViorel

## Command:
```
$ for ITEM in $(cat values_to_search.txt); do  (egrep $ITEM full_values_list.txt && echo $ITEM found) | grep "found" >> exit_FOUND.txt; done
```

## Explanation:
No explanation available

## Limitations:
No limitations specified

