# Function to extract columns from an input stream

## Command:
```
$ col() { awk '{print $('$(echo $* | sed -e s/-/NF-/g -e 's/ /),$(/g')')}'; }
```

## Explanation:
Explanation
A slightly improved version of the original one-liner to allow negative indexes to extract columns relative to the end of the line, for example:
$ echo a b c | col 1 -0 -1
a c b

In this example the function expands to:
awk '{print $(1), $(NF-0), $(NF-1)}'

## Limitations:
No limitations specified

