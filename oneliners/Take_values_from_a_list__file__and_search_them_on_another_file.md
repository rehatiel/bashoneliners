# Take values from a list (file) and search them on another file

## Command:
```
$ for ITEM in $(cat values_to_search.txt); do  (egrep $ITEM full_values_list.txt && echo $ITEM found) | grep "found" >> exit_FOUND.txt; done
```

## Explanation:
Explanation
This line :) searches values taken from a file (values_to_search.txt) by scanning a full file values list . If value found, it is added on a new file exit_FOUND.txt.
Alternatively, we can search for values from the list 1 which does NOT exists on the list 2, as bellow:
for ITEM in $(cat values_to_search.txt); do  (egrep $ITEM full_values_list.txt || echo $ITEM not found) | grep "not found">> exit_not_found.txt; done

## Limitations:
No limitations specified

