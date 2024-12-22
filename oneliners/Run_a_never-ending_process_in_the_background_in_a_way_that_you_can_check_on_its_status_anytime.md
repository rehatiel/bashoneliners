# Run a never-ending process in the background in a way that you can check on its status anytime

## Command:
```
$ screen -d -m -S some_name ping my_router
```

## Explanation:
Explanation

-d -m start screen in "detached" mode. This creates a new session but doesn't  attach  to  it. 
-S some_name gives the screen session a label, so you can easily re-attach to it with screen -R some_name
The shell prompt returns immediately, and of course you can logout too, the screen session will continue to run happily.
When the specified program exits (in this example ping), its screen window will also exit, and if there are no other windows in the screen session, then the screen session itself will also exit.

## Limitations:
No limitations specified

