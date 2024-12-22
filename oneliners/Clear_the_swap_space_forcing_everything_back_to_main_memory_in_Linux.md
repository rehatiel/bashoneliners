# Clear the swap space forcing everything back to main memory in Linux

## Command:
```
$ sudo swapoff -a; sudo swapon -a
```

## Explanation:
Explanation
Note: if you don't have enough main memory the swapoff will fail.

## Limitations:
Limitations
This works only in Linux.

