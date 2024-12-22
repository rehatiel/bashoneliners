# Open another terminal at current location

## Command:
```
$ $TERMINAL & disown
```

## Explanation:
Explanation
Opens another terminal window at the current location.
Use Case
I often cd into a directory and decide it would be useful to open another terminal in the same folder, maybe for an editor or something. Previously, I would open the terminal and repeat the CD command.
I have aliased this command to open so I just type open and I get a new terminal already in my desired folder.
The & disown part of the command stops the new terminal from being dependant on the first meaning that you can still use the first and if you close the first, the second will remain open.

## Limitations:
Limitations
It relied on you having the $TERMINAL global variable set. If you don't have this set you could easily change it to something like the following:
gnome-terminal & disown
or
konsole & disown

