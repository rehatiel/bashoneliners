# Have script run itself in a virtual terminal

## Command:
```
$ tty >/dev/null || { urxvt -hold -e "$0" "$@" & exit; }
```

## Explanation:
Explanation
This can be the first line of a script that will be clicked from a graphical user interface in X to make it open up a virtual terminal to display output. If a terminal is already open it will run in the current terminal. It assumes urxvt and uses the hold option to keep from closing, both of which could be substituted for such as rxvt or add read at the end of the script.

It's a single line if statement that checks the exit code of tty which prints the current terminal name usually nothing under X.
The curly braces are needed for grouping.
A space is required after the opening brace { and a semicolon is required before the closing brace }.
Replacing what would be a semicolon, the ampersand & forks the terminal command to a second process and the launching script exits right away.
-e feeds to the terminal application the expression of $0which holds the path of the script itself and $@, the entire set of quoted arguments.

## Limitations:
Limitations
If the script is large, say several gigabytes and the system tries to make two copies of the script, twice the size of RAM or memory will be needed for loading it.

rxvt -e will kill any subprocesses at the end

