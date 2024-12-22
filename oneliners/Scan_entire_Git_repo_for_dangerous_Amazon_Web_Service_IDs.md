# Scan entire Git repo for dangerous Amazon Web Service IDs

## Command:
```
$ git grep -Ew '[A-Z0-9]{20}'
```

## Explanation:
Explanation
Letting your AWS credentials escape is very dangerous! This simple tool makes sure none of your secrets make into version control and therefore out into the hands of evil robots.
Use Git to quickly search for things that look like AWS IDs: a 20-character uppercase word. The -w adds word boundaries around the search pattern, and the -E make it possible to use extended regex syntax, in this example the {20} count.

## Limitations:
No limitations specified

