# dark_axl

## Command:
```
$ for i in $(cat /var/log/vsftpd.log | grep $DATE_TIME | grep UPLOAD | grep OK); do ls /FTP/HOME/$i >> /dev/null 2> \&1; if \[ $? = 0 \]; then echo "$i" >> $FILES_OK_UPLOADS.log; else  echo "$DATE ERROR: File $i not found" >> $FTP_FILES_NOTOK_$DATE_TIME.log; fi; done
```

## Explanation:
Explanation
This one-liner checks and validates the received files via ftp, and generates a log of these files. To have a record of files received and be able to process, based on the successful transfer and the existence of the files.

## Limitations:
No limitations specified

