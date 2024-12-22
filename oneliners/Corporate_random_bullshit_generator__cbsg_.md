# Corporate random bullshit generator (cbsg)

## Command:
```
$ curl -s http://cbsg.sourceforge.net/cgi-bin/live | grep -Eo '^<li>.*</li>' | sed s,\</\\?li\>,,g | shuf -n 1
```

## Explanation:
Explanation
This one-liner will just use cbsg.sourceforge.net/cgi-bin/live and grab one random corporate bullshit.
Good to use when deprecating command line tools in your corporation :-)

## Limitations:
Limitations
I don't think cowsay is installed by default on a mac although it can be installed with brew cowsay

