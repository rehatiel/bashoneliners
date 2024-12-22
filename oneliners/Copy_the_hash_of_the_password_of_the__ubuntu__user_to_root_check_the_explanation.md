# Copy the hash of the password of the "ubuntu" user to root check the explanation

## Command:
```
$ passwd
```

## Explanation:
Explanation
Copy hashed password form /etc/shadow and user "ubuntu" to root password
the idea is to make the password of the user ubuntu to be the same as root.
ubuntu is the username so if you want to be on your specific user you need to change it.
here is the command : 'sed -i "s|root:*|root:cat /etc/shadow |grep ^ubuntu | awk -F':' '{print $2}'|g" /etc/shadow
use `  (the sign ~ without shift)
before cat
and ` after '{print $2}'
root:* search for specific string "root:*"
^ubuntu -username
cat /etc/shadow |grep ^ubuntu | awk -F':' '{print $2}' - takes the password

## Limitations:
Limitations
Works ONLY IF 
root DOEASN'T have PASSWORD and in the file is like this root:*: ../doeasn't matter/

