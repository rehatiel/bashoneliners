# Halt the system in Linux without the halt command or gui

## Command:
```
$ echo o > /proc/sysrq-trigger
```

## Explanation:
Explanation

First you need to enable the sysrq interface with: echo 1 > /proc/sys/kernel/sysrq
echo o > /proc/sysrq-trigger halts
echo b > /proc/sysrq-trigger reboots

## Limitations:
No limitations specified

