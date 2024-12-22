# laurip

## Command:
```
$ atq | sed 's_\([0-9]\{1,8\}\).*_\1_g' | xargs atrm
```

## Explanation:
Explanation
It asks all jobs from atq, then parses a number with 1-8 digits (job id), then forwards that number via xargs to atrm

## Limitations:
Limitations
Only works with job id-s of up to 8 digits, but if you can find the 8, you can get around that.

