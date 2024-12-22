# Really lazy way to print the first instance of $foo that occurs after $bar

## Command:
```
$ ifconfig | grep ^en1 -A5 | grep inet | head -n 1
```

## Explanation:
Explanation
This is just for the sake of an example of finding $foo that occurs after $bar. Substitute ifconfig and the arguments of grep appropriately for your use case.

In the output of ifconfig there are several lines with inet. We want to get to the first one that comes after a line starting with en1
grep ^en1 -A5 will print the line starting with en1 and the next 5 lines that follow it
grep inet will print only the lines matching inet
head -n 1 will print only the first line

The value 5 in -A5 is really just a guess that the line we're interested in will be within the next 5 lines, the appropriate number depends on your use case.
Kind of a dumb technique, but it's easy to remember.

## Limitations:
No limitations specified

