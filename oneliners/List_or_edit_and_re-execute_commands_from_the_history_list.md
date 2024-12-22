# List or edit and re-execute commands from the history list

## Command:
```
$ fc -l
```

## Explanation:
Explanation
fc is a little known but very useful bash built-in.

fc -l will list the most recent 16 commands
fc will open the last command in a text editor defined in the environmental variable FCEDIT or EDITOR or else vi, and re-execute when you exit
fc 5 9 will open the history entries 5 to 9 in a text editor
fc -s pat=sub will run the last command after substituting pat with sub in it (does not open editor)
fc -s pat=sub cc is the same but on the last command starting with cc
fc -s cc will run the last command starting with cc

For more info see help fc.

## Limitations:
No limitations specified

