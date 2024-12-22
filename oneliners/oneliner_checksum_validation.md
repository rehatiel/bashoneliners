# oneliner checksum validation

## Command:
```
$ sha512sum filename.iso | grep -oE ".*\ " | (read checksum; [ "$Checksum" ==  checksumCheck ] && printf "\033[0;32mValid" || printf "\033[0;31mInvalid")
```

## Explanation:
Explanation
this oneliner will verify the checksum of a file and compare it with provided checksum.
In the script, you can substitute 
filename.iso with debian-11.4.0-amd64-netinst.iso
checksumCheck with eeab770236777e588f6ce0f984a7f3e85d86295625010e78a0fca3e873f78188af7966b53319dde3ddcaaaa5d6b9c803e4d80470755e75796fbf0e96c973507f

## Limitations:
No limitations specified

