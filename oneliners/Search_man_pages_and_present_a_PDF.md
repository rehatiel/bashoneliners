# Search man pages and present a PDF

## Command:
```
$ man -k . | awk '{ print $1 " " $2 }' | dmenu -i -p man | awk '{ print $2 " " $1 }' | tr -d '()' | xargs man -t | ps2pdf - - | zathura -
```

## Explanation:
Explanation
This uses dmenu to search through your man pages then produces a pdf for the one you selected

man -k . lists all man pages
awk '{ print $1 " " $2 }' prints the first column, a space then the second column
This results in lines like this: curl (1)


dmenu -i -p man takes a list from stdin and lets you choose one. It returns what you chose
You can swap dmenu for something like rofi if required


awk '{ print $2 " " $1 }' puts the second column first
The output is now like (1) curl


tr -d '()' removes the parentheses
xargs man -t puts the result at the end of the command man -t
This makes the command something like man -t 1 curl
the -t flag makes man use troff to format the page


ps2pdf - - produces a PDF from the postscript output by the previous command
zathura - is a PDF reader that can read STDIN

## Limitations:
Limitations
You will need a PDF viewer that can read from STDIN
You will need ps2pdf installed which is part of ghostscript
You will need dmenu or a dmenu compatible program installed.
Almost all systems will already have xargs, tr troff, awk installed.

