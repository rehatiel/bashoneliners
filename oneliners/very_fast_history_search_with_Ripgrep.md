# very fast history search with Ripgrep

## Command:
```
$ rh() { rg "$1" ~/.bash_history }
```

## Explanation:
Explanation
I search my history a lot. At 65k lines, this can take a while.  Recently I've installed Ripgrep, which is much faster than my previous favorite Ack, and faster than good old Grep/Egrep.
After defining the above function, history searches are much faster!
Example: I forgot how to hit my service's endpoint. Instead of grepping through the Bash history file, I use my new Ripgrep-powered function:
rh curl.*health

## Limitations:
Limitations
This function only works if you have Ripgrep installed
It's not really needed unless you have "infinite history" turned on.

