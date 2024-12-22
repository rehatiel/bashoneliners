# Random Git Commit

## Command:
```
$ git commit -m "$(w3m whatthecommit.com | head -n 1)"
```

## Explanation:
Explanation
This will commit a message pulled from What the Commit.
-m allows you to provide the commit message without entering your editor
w3m is a terminal based web browser.  We basically use it to strip out all of the html tags
head -n 1 will grab only the first line

## Limitations:
Limitations
This requires you to have w3m installed

