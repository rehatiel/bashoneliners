# Ban all IPs that attempted to access phpmyadmin on your site

## Command:
```
$ grep "phpmyadmin" $path_to_access.log | grep -Po "^\d{1,3}\.\d{1,3}\.\d{1,3}\.\d{1,3}" | sort | uniq | xargs -I% sudo iptables -A INPUT -s % -j DROP
```

## Explanation:
Explanation
Cheap security Bash one-liner to ban all IPs that are probably doing automated attacks.
Make sure your IP isn't listed before piping through iptables drop!!


This will first find all lines in $path_to_access.log that have phpmyadmin in them, 


Then grep out the ip address from the start of the line,


Then sort and unique them, 


Then add a rule to drop them in iptables


Again, just edit in echo % at the end instead of the iptables command to make sure your IP isn't in there. Don't inadvertently ban your access to the server!

## Limitations:
Limitations
You may need to change the grep part of the command if you're on mac or any system that doesn't have grep -P.

