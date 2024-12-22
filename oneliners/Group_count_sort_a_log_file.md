# Group count sort a log file

## Command:
```
$ A=$(FILE=/var/log/myfile.log; cat $FILE | perl -p -e 's/.*,([A-Z]+)[\:\+].*/$1/g' | sort -u | while read LINE; do grep "$LINE" $FILE | wc -l | perl -p -e 's/[^0-9]+//g'; echo -e "\t$LINE"; done;);echo "$A"|sort -nr
```

## Explanation:
Explanation

SQL: SELECT COUNT(x), x FROM y GROUP BY x ORDER BY count DESC;
BASH: a temp var for the last sort: $A=$( 
the file you want: FILE=/var/log/myfile.log 
dump the file to a stream: cat $FILE | 
cut out the bits you want to count: perl -p -e 's/.*,([A-Z]+)[\:\+].*/$1/g' | 
get a unique list: sort -u | 
for each line/value in the stream do stuff: while read LINE; do
dump all lines matching the current value to an inner stream: grep "$LINE" $FILE |
count them: wc -l | 
clean up the output of wc and drop the value on stdout: perl -p -e 's/[^0-9]+//g';
drop the current value to stdout: echo -e "\t$LINE";
finish per value operations on the outer stream: done;
finish output to the temp var: );
dump the temp var to a pipe: echo "$A" |
sort the list numerically in reverse: sort -nr

## Limitations:
No limitations specified

