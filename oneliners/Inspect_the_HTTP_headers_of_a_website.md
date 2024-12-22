# Inspect the HTTP headers of a website

## Command:
```
$ curl -I amazon.com
```

## Explanation:
Explanation
With the -I (capital "i") flag, curl downloads only the page headers without content, in the above example:
HTTP/1.1 301 Moved Permanently
Server: Server
Date: Fri, 08 Feb 2019 21:48:23 GMT
Content-Type: text/html
Content-Length: 179
Connection: keep-alive
Location: https://amazon.com/

If you want to skip redirects and get to the "real" content, you can add the -L flag.
It works recursively. In the above example, at the time of this writing amazon.com redirects to https://amazon.com, which in turn redirects to https://www.amazon.com.

## Limitations:
No limitations specified

