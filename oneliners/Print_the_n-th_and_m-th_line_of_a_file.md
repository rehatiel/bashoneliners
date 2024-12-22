# Print the n-th and m-th line of a file

## Command:
```
$ sed -ne '101 p' -e '106 p' /path/to/the/file
```

## Explanation:
Explanation

The above command will print the 101th and 106th lines of the specified file.
The -n switch will make sed not print all lines by default.
The -e switch is to specify a sed command, you can use it multiple times at once.

Some sed command examples:

45 p - print line #45
34,55 p - print lines #34-#55
99,$ p - print lines #99-end of the file

## Limitations:
No limitations specified

