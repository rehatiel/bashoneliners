# Elkku

## Command:
```
$ echo {01..10}
```

## Explanation:
Explanation
This example will print:
01 02 03 04 05 06 07 08 09 10

While the original one-liner is indeed IMHO the canonical way to loop over numbers, the brace expansion syntax of Bash 4.x has some kick-ass features such as correct padding of the number with leading zeros.

## Limitations:
Limitations
The zero-padding feature works only in Bash >=4.

