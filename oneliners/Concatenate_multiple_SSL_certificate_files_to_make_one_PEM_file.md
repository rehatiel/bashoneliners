# Concatenate multiple SSL certificate files to make one PEM file

## Command:
```
$ files=("yourcert.crt" "provider.ca.pem") && for i in ${files[@]} ; do $(cat $i >> yourcert.pem && echo "" >> yourcert.pem) ; done
```

## Explanation:
Explanation
If you want to concat multiple files, you might end up with cat {a,b,c} >> yourcert.pem  in a loop. But the problem is that it doesnt create new line after each cat.
This script is for that matter.
To use, e.g.:
cd /etc/ssl/certs
files=("yourcert.crt" "provider.ca.pem") && for i in ${files[@]} ; do $(cat $i >> yourcert.pem && echo "" >> yourcert.pem) ; done

## Limitations:
No limitations specified

