# Print the list of your Git commits this month

## Command:
```
$ git log --since='last month' --author="$(git config user.name)" --oneline
```

## Explanation:
Explanation

--since='last month' sets the start of the period, in this case the end of the previous month. Other interesting examples: midnight, 2 weeks ago. When the date parameter contains a space, it must be quoted, naturally.
--author="$(git config user.name)" filters commits matching a specific author, in this example yourself, looking up your full name from your Git configuration.
--oneline makes the output compactly one line per commit

## Limitations:
No limitations specified

