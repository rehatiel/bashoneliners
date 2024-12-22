# Force the preferred language when downloading a web page with wget

## Command:
```
$ wget -–header='Accept-Language: en-us' http://www.timeanddate.com/calendar/index.html?year=2008&country=26 -O calendar.html
```

## Explanation:
Explanation
When downloading web pages with wget, some websites try to be smart and detect your preferred language based on geographical location of your IP address. This can be a problem if for example you are in Japan but you want to download a page in English.

## Limitations:
No limitations specified

