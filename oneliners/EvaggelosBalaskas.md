# EvaggelosBalaskas

## Command:
```
$ for i in *; do mv "$i" "${i^^}"; done
```

## Explanation:
Explanation
Loop over the items in the current directory, and use Bash built-in case modification expansion to convert to upper case.

## Limitations:
Limitations
The case modification extension is available since Bash 4.

