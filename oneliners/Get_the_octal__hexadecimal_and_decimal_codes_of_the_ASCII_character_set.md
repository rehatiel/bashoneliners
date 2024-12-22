# Get the octal, hexadecimal and decimal codes of the ASCII character set

## Command:
```
$ man ascii
```

## Explanation:
Explanation
Knowing the octal, hexadecimal or decimal code of the ASCII character set can be handy at times. In the past, too often I did things like:
perl -e 'for my $n (1 .. 255) { print $n, chr($n), $n, "\n"; }'

... when a simple man ascii would have done the trick...
On a related note, these all print the letter "A":
echo -e '\0101'
printf '\101'
printf '\x41'
perl -e 'print "\x41"'

## Limitations:
No limitations specified

