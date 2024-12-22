# Move file and cd with one command

## Command:
```
$ mv file dir && cd "$_"  && pwd
```

## Explanation:
Explanation
This one liner allows you to move a file or directory and cd the to the destination of the move.
The "$_" repeats the last argument dir, this allows it to take the command cd and execute, pwd is just to show you where you are.
function name()
{ mv "$1" "$2" && cd "$_" && pwd 
}
This function will do the same thing.
I got tired of always moving files from my Downloads folder only to cd to the destination and start working on it. The mv can be substituent with cp as well.

## Limitations:
Limitations
Can only do one file or dir at a time. Haven't figured out how to multiple file moves to one directory.

