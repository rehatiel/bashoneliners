# Check if a text snippet is valid C code

## Command:
```
$ gcc -fsyntax-only -xc - <<< "text snippet"
```

## Explanation:
Explanation
-fsyntax-only is to check the code for syntax errors, and don't do anything beyond that.
-xc is to specify C language. Other interesting option for example c++. This flag is mandatory when reading from stdin.
- is to read text from stdin.
<<< is to redirect text to stdin of a command, also known as a here string. You can read more about this in man bash in the Here Strings section.
Note that "text snippet" must be enclosed within double-quotes, otherwise only the first word will be part of the here string, the rest will be interpreted as additional command line arguments to the gcc program.

## Limitations:
No limitations specified

