# Check that a directory is a parent of another

## Command:
```
$ is_parent() { [[ "$2" =~ $1/? ]]; }
```

## Explanation:
Explanation
The function expanded would look like this :
T() {
    if [[ "$2" =~ $1/? ]]; then
        echo "$2 is child of $1"
        return 0
    else
        echo "$2 is NOT child of $1 ($?)"
        return 1
    fi
}

## Limitations:
No limitations specified

