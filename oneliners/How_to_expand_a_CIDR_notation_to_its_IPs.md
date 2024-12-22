# How to expand a CIDR notation to its IPs

## Command:
```
$ for j in $(seq 0 255); do for i in $(seq 0 255) ; do seq -f "10.$j.$i.%g" 0 255; done; done
```

## Explanation:
Explanation
Using two for loops to create second & third block of IP and finally through a formatted seq to printf the output.
More efficient/using less memory than using {..} (range).

## Limitations:
Limitations
seq is not available by default in some systems.

