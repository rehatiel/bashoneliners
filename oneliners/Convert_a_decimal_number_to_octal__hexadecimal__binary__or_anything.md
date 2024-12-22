# Convert a decimal number to octal, hexadecimal, binary, or anything

## Command:
```
$ echo 'obase=2;1234' | bc
```

## Explanation:
Explanation

bc is an arbitrary precision calculator language.
obase defines the conversion base for output numbers, in this example 2 (binary)
; is a statement separator in bc
1234 is the decimal number to convert
By piping the command to bc we get 1234 in binary format

## Limitations:
No limitations specified

