# Convert text from decimal to little endian hexadecimal

## Command:
```
$ echo $(printf %08X 256 | grep -o .. | tac | tr -d '\n')
```

## Explanation:
Explanation
example of 256
printf %08X produces the 8 characters 00000100
grep breaks string by two characters
tac reverses
tr 00010000

## Limitations:
Limitations
could be put in a loop like this
for A in $(printf %08X'\n' 256 255); do echo $A | grep -o .. | tac | tr -d '\n'; done

