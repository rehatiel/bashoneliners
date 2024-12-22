# openiduser162

## Command:
```
$ #!/bin/bash echo Please enter an Ip Address read ipaddress iptables -A INPUT -s $ipaddress -j DROP echo "The ip Address $ipaddress was sucessfuly blocked"
```

## Explanation:
Explanation
!/bin/bash
echo Please enter an Ip Address (This line prompts the user for an ipaddress)
read ipaddress(this line reads the users input and sets it as a variable)
iptables -A INPUT -s $ipaddress -j DROP (this line runs the iptables command that blocks the ipaddress)
echo "The ip Address $ipaddress was sucessfuly blocked"(this line prints the ip address and lets the user know it was successfuly blocked)

## Limitations:
No limitations specified

