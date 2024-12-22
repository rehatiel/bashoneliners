# Get the HTTP status code of a URL

## Command:
```
$ curl -Lw '%{http_code}' -s -o /dev/null -I SOME_URL
```

## Explanation:
Explanation

-w '%{http_code}' is to print out the status code (the meat of this post)
-s is to make curl silent (suppress download progress stats output)
-o /dev/null is to redirect all output to /dev/null
-I is to fetch the headers only, no need for the page content
-L is to follow redirects

## Limitations:
No limitations specified

