# Insert lines from one text file to another one

## Command:
```
$ sed -re ':a;Rfile1' -e 'x;s/^/./;/.{10}/!{x;ba};s/.*//;x' file2
```

## Explanation:
Explanation
This command reads the first line from file2 and then 10 lines from file1, then the second line from file2 and the next 10 lines from file1 and so on.

## Limitations:
Limitations
Works in GNU sed.

