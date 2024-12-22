# Generate a sequence of numbers

## Command:
```
$ for ((i=1; i<=10; ++i)); do echo $i; done
```

## Explanation:
Explanation
This is similar to seq, but portable. seq does not exist in all systems and is not recommended today anymore. Other variations to emulate various uses with seq:
# seq 1 2 10
for ((i=1; i<=10; i+=2)); do echo $i; done

# seq -w 5 10
for ((i=5; i<=10; ++i)); do printf '%02d\n' $i; done

## Limitations:
Limitations
The zero-padding feature works only in Bash >=4.

