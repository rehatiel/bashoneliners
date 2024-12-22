# Converts DD/MM/YYYY date format to ISO-8601 (YYYY-MM-DD)

## Command:
```
$ sed 's_\([0-9]\{1,2\}\)/\([0-9]\{1,2\}\)/\([0-9]\{4\}\)_\3-\2-\1_g'
```

## Explanation:
Explanation
Works on dates such as 01/02/1993, 01/10/1991, etc converting them to the superior ISO-8601 date format giving us 1993-02-01 and 1991-10-01 respectively.
Test:
     echo '27/05/1994' | pattern given above 
Outputs 
1994-05-27

## Limitations:
Limitations
Currently does not fully convert  D/M/YYYY dates such as 1/2/1993 to 1993-02-01, but 1993-2-1

