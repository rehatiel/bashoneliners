# Set a colorful bash prompt per dev test prod environments

## Command:
```
$ PS1='\[\e[1;31m\][\u@\h \W]\$\[\e[0m\] '
```

## Explanation:
Explanation
It is useful to set a different color for the shell prompt in different deployment environments like dev/test/production, so that you don't mix up your multiple windows and do something by accident in the wrong window.

PS1 contains the format of the primary prompt
\[\e[1;31m\] sets the foreground color to red
\u will be substituted with the current username
\h will be substituted with the hostname
\W will be substituted with the current directory name
\[\e[0m\] is the end marker of the color setting

To make the color stand out even more for root users, the inverse color can be interesting too:
PS1='\[\e[7;31m\][\u@\h \W]\$\[\e[0m\] '

Other color examples:
#PS1='\[\e[1;32m\][\u@\h \W]\$\[\e[0m\] ' # green
#PS1='\[\e[1;33m\][\u@\h \W]\$\[\e[0m\] ' # yellow
#PS1='\[\e[1;34m\][\u@\h \W]\$\[\e[0m\] ' # blue

You can learn more in man bash, search for "PROMPTING".

## Limitations:
Limitations
Your terminal program must support colors, of course ;-)

