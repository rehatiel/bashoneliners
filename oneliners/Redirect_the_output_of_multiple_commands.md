# Redirect the output of multiple commands

## Command:
```
$ { cmd1 ; cmd2 ; cmd3 ; } > out.out 2> err.out
```

## Explanation:
Explanation

Curly braces are very helpful for grouping several commands together
Be careful with the syntax: 1. there must be whitespace after the opening brace 2. there must be a semicolon after the last command and before the closing brace
Another practical use case: test something || { echo message; exit 1; }

## Limitations:
No limitations specified

