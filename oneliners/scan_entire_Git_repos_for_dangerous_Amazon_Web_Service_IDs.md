# scan entire Git repos for dangerous Amazon Web Service IDs

## Command:
```
$ git ls-tree --full-tree -r --name-only HEAD | xargs egrep -w '[A-Z0-9]{20}'
```

## Explanation:
Explanation
Letting your AWS credentials escape is very dangerous! This simple tool makes sure none of your secrets make into version control and therefore out into the hands of evil robots.
Use Git to quickly list all files in the repos. Then, take this list and search for things that look like AWS IDs: a 20-character uppercase word.

## Limitations:
No limitations specified

