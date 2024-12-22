# `less` is more convenient with the `-F` flag

## Command:
```
$ less -F FILE1
```

## Explanation:
Explanation
less is a "pager" program like more, with a lot of added features. By default, to exit less you have to press q. This can be annoying when viewing a small file that would fit on the screen.
The -F flag to the rescue! When started with the -F flag, less will quit if the entire input (whether from stdin or a file) fits on a single screen.
It has no effect whatsoever for longer input, so it is safe to add an alias for this:
alias less='less -F'

## Limitations:
No limitations specified

