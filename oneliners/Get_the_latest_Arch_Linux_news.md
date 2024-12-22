# Get the latest Arch Linux news

## Command:
```
$ w3m https://www.archlinux.org/ | sed -n "/Latest News/,/Older News/p" | head -n -1
```

## Explanation:
Explanation
w3m is a terminal web browser. We use it to go to https://www.archlinux.org/
We then use sed to capture the text between Latest News and Older News.
We then get rid of the last line which is Older News.

## Limitations:
Limitations
For this, w3m would need to be installed. It should be installable on most systems.
If Arch change the format of there website significantly, this might stop working.

