# Find video files cached by the flash plugin in browsers

## Command:
```
$ file /proc/*/fd/* 2>/dev/null | grep Flash | cut -f1 -d:
```

## Explanation:
Explanation
Recent versions of the flash plugin hide the temporary file by marking it deleted. Practically the video stream is downloaded to a "deleted file". However, even when a file is deleted, if the file is opened by a process then you can find its file descriptor and consequently the file contents. 
This simple script prints out the file descriptors of opened Flash videos:
file /proc/*/fd/* 2>/dev/null | grep Flash | cut -f1 -d:

And, you probably want to create a regular file from the file descriptor, for example:
cp $(file /proc/*/fd/* 2>/dev/null | grep Flash | cut -f1 -d: | head -n 1) video.avi

Otherwise the file descriptor is not very convenient (remember, it's a deleted file!)
The method should work regardless of your browser.

## Limitations:
No limitations specified

