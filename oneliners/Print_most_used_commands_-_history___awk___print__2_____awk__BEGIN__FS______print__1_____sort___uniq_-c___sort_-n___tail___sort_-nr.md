# Print most used commands - history | awk '{print $2}' | awk 'BEGIN {FS="|"}{print $1}' | sort | uniq -c | sort -n | tail | sort -nr

## Command:
```
$ history | awk '{print $2}' | awk 'BEGIN {FS="|"}{print $1}' | sort | uniq -c | sort -n | tail | sort -nr
```

## Explanation:
Explanation
72 exit
 64 cd
 45 sudo
 26 ls
 24 halt
 21 vim
 16 ll
 12 xdg-mime
 12 mv
 12 ln

## Limitations:
Limitations
From http://archive.fo/WfXDS

