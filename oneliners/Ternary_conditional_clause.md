# Ternary conditional clause

## Command:
```
$ [ test_statement ] && ( then_statement ) || ( else_statement );
```

## Explanation:
Explanation
The test_statement is under a child process (a.k.a. subshell), which will return a boolean output. The then_statement depends on the former to be executed. Otherwise, it will be done upon the latter.

## Limitations:
No limitations specified

