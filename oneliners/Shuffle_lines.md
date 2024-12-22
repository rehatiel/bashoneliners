# Shuffle lines

## Command:
```
$ ... | perl -MList::Util -e 'print List::Util::shuffle <>'
```

## Explanation:
Explanation
Sorting lines is easy: everybody knows the sort command.
But what if you want to do the other way around?
The above perl one-liner does just that:

-MList::Util load the List::Util module (as if doing use List::Util inside a Perl script)
-e '...' execute Perl command
print List::Util::shuffle <> call List::Util::shuffle for the lines coming from standard input, read by <>

Another way would be sort -R if your version supports that (GNU, as opposed to BSD). In BSD systems you can install coreutils and try gsort -R instead. (For eample on OSX, using MacPorts: sudo port install coreutils.)

## Limitations:
No limitations specified

