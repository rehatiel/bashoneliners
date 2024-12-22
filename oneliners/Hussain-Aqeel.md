# Hussain-Aqeel

## Command:
```
$ sha512sum filename.iso | grep -oE ".*\ " | (read checksum; [ "$Checksum" ==  checksumCheck ] && printf "\033[0;32mValid" || printf "\033[0;31mInvalid")
```

## Explanation:
No explanation available

## Limitations:
No limitations specified

