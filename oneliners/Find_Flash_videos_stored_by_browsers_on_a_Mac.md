# Find Flash videos stored by browsers on a Mac

## Command:
```
$ find /private/ 2>/dev/null | grep /Flash
```

## Explanation:
Explanation
When you watch a flash video like youtube in a browser, the video file is saved on your harddisk at a temporary location. And, if you watch a video and then another video in the same window, the first one will be deleted.

## Limitations:
Limitations

Might not work with all browsers. 
Does not work with all websites (for example IMDB).
Does not work with an anonymous window in Chrome.

