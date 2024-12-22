# Send a file by email as attachment

## Command:
```
$ uuencode /var/log/messages messages.txt | mailx -s "/var/log/messages on $HOST" me@example.com
```

## Explanation:
Explanation

uuencode /var/log/messages messages.txt -- the first parameter is the file to attach, the second is the filename to use for the attachment
mailx -s subject emailaddress -- takes standard input as the content of the email

## Limitations:
No limitations specified

