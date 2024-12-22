# Get the available space on a partition as a single numeric value

## Command:
```
$ df /path/to/dir | sed -ne 2p | awk '{print $4}'
```

## Explanation:
Explanation

sed -ne 2p prints the 2nd line
awk '{print $4}' prints the 4th column

## Limitations:
Limitations
The output of the df command might be different depending on the system, and the available space might not be the 4th column. Make the necessary adjustments depending on your system.

