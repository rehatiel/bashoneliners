# openiduser81

## Command:
```
$ ... | perl -MList::Util=shuffle -e 'print shuffle <>;'
```

## Explanation:
Explanation
Sorting lines is easy: everybody knows the sort command.
But what if you want to do the other way around? The above perl one-liner does just that:

-MList::Util=shuffle load the shuffle function from the List::Util package
-e '...' execute Perl command
print shuffle <> call List::Util::shuffle for the lines coming from standard input, read by <>

## Limitations:
No limitations specified

