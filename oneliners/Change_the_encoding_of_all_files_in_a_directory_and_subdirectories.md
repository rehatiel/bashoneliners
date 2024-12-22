# Change the encoding of all files in a directory and subdirectories

## Command:
```
$ find . -type f  -name '*.java' -exec sh -c 'iconv -f cp1252 -t utf-8 "$1" > converted && mv converted "$1"' -- {} \;
```

## Explanation:
Explanation
The parameters of find:

. -- search in the current directory, and its subdirectories, recursively
-type f -- match only files
-name '*.java' -- match only filenames ending with .java
-exec ... \; -- execute command

The command to execute is slightly complicated, because iconv doesn't rewrite the original file but prints the converted content on stdout. To update the original file we need 2 steps:

Convert and save to a temp file
Move the temp file to the original

To do these steps, we use a sh subshell with -exec, passing a one-liner to run with the -c flag, and passing the name of the file as a positional argument with -- {}.
Unfortunately the redirection will use UNIX style line endings. If the original files have DOS style line endings, add this command in the subshell:
vim +'set ff=dos' +wq converted

## Limitations:
No limitations specified

