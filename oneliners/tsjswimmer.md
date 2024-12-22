# tsjswimmer

## Command:
```
$ cat file.url | grep -i url=* | cut -b 5- | xargs firefox
```

## Explanation:
Explanation
Basically the same as my other command, except the URL is piped to Firefox using xargs, as opposed to being put in parenthesis with a dollar sign.

## Limitations:
Limitations
This hack has not been tested with URL's which use "specail characters" (quotes, semi-colons, ect), except ampersands, percent signs, and question marks. Tested only on gnu/linux (using bash and sh).

