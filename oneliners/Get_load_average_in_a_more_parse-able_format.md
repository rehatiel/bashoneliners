# Get load average in a more parse-able format

## Command:
```
$ python -c 'import os; print os.getloadavg()[0]'
```

## Explanation:
Explanation
In short, it runs a Python one-line script which imports the 'os' module and uses it to get the load average. It then indexes into a tuple, using the index of zero. The tuple is like this: (one-minute-average, five-minute-average, fifteen-minute-average), so you could substitute 0 for 1 to get the five minute load average, or 2 to get the fifteen minute load average. I find this really useful when writing larger bash one-liners which require this information, as I don't have to parse the output of uptime.

## Limitations:
Limitations
Requires Python.

