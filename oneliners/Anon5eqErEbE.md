# Anon5eqErEbE

## Command:
```
$ grep -l 'baz' $(grep -l 'bar' $(grep -lr 'foo' *) )
```

## Explanation:
Explanation
Most people familiar with extended regular expressions know you can use the pipe symbol | to represent "or", so to see files containing any of "foo", "bar", or "baz" you could run:
grep -Elr 'foo|bar|baz' *
There is no corresponding symbol representing "and", but you can achieve the same effect by nesting invocations to grep.  grep -lr 'foo' * returns a list of filenames in or below the current directory containing "foo".  Via the $( ... ) syntax, this list is then operated on by grep -l 'bar', returning a list of filenames containing both 'foo' and 'bar', which finally is operated on by grep -l "baz".  The end result is a list of filenames containing all three terms.

## Limitations:
Limitations
This one-liner results in scanning files multiple times.  You will want to put the term you expect to match the fewest number of times farthest to the right (that is, in the same position as "foo") and the one you expect to match most frequently farthest to the left (the same position as "baz").  This way, you will weed out the largest number of files sooner, making the one-liner complete more quickly.

