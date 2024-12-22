# Remove .DS_Store from the repository you happen to staging by mistake

## Command:
```
$ find . -name .DS_Store -exec git rm --ignore-unmatch --cached {} +
```

## Explanation:
Explanation
Actual conditions without erasing, remove from the repository.

## Limitations:
No limitations specified

