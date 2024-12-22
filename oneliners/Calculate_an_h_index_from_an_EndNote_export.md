# Calculate an h index from an EndNote export

## Command:
```
$ MAX=$(NUM=1;cat author.xml |perl -p -e 's/(Times Cited)/\n$1/g'|grep "Times Cited" |perl -p -e 's/^Times Cited:([0-9]*).*$/$1/g'|sort -nr | while read LINE; do if [ $LINE -ge $NUM ]; then echo "$NUM"; fi; NUM=$[$NUM+1]; done;); echo "$MAX"|tail -1
```

## Explanation:
Explanation
EndNote?! I know but sometimes we have windows users as friends

## Limitations:
No limitations specified

