# Run command multiple times with a for loop and a sequence expression

## Command:
```
$ for i in {1..10}; do date; sleep 1; done
```

## Explanation:
Explanation
This is just a regular for loop with a sequence expression. A sequence expression has the form {x..y[..incr]}, where x and y are either integers or single characters, and incr an optional increment.
More examples:

{a..f} = a b c d e f
{a..f..2} = a c e
{0..1}{0..1} = 00 01 10 11

## Limitations:
Limitations
Don't try a large range like {1..10000000000000000}, it may render your computer unusable until killed.

