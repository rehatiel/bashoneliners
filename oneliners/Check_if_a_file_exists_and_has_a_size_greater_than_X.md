# Check if a file exists and has a size greater than X

## Command:
```
$ [[ $(find /path/to/file -type f -size +51200c 2>/dev/null) ]] && echo true || echo false
```

## Explanation:
Explanation

The find takes care two things at once: checks if file exists and size is greater than 51200.
We redirect stderr to /dev/null to hide the error message if the file doesn't exist.
The output of find will be non-blank if the file matched both conditions, otherwise it will be blank
The [[ ... ]] evaluates to true or false if the output of find is non-blank or blank, respectively

You can use this in if conditions like:
if [[ $(find /path/to/file -type f -size +51200c 2>/dev/null) ]]; do
    somecmd
fi

## Limitations:
No limitations specified

