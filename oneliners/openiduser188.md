# openiduser188

## Command:
```
$ behave -d | grep "scenarios passed" | cut -d, -f4 | sed -e 's/^[[:space:]]*//' | sed 's/untested/scenarios/g'
```

## Explanation:
Explanation
behave -d

-d stands for dry-run, so behave invokes formatters without executing the steps.
grep "scenarios passed"

Then we grep for the summary line containing number of all scenarios
cut -d, -f4

then we cut the last value from selected summary line that show how many scenarios were "untested" (in this context it means not executed, which is exactly what we need)
sed -e 's/^[[:space:]]*//'

Trim leading space
sed 's/untested/scenarios/g'

Lastly simple sed to replace untested with scenarios

## Limitations:
No limitations specified

