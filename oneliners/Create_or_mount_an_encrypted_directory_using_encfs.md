# Create or mount an encrypted directory using encfs

## Command:
```
$ encfs -i 5 $PWD/raw $PWD/content
```

## Explanation:
Explanation
The first time you run this, it will create an encrypted directory raw in the current working directory, and mount it on directory content in the same directory. It will ask a couple of questions:

Create directory "raw" ? -- answer "y"
Create directory "content" ? -- answer "y"
Choose configuration mode -- press enter, or "p" for "paranoia mode"

The content directory will be visible and editable only by your user, and all the files you put inside will be saved encrypted under raw. The encrypted data is only visible when raw is mounted somewhere. 
The -i 5 means the content directory will be automatically unmounted after being idle for 5 minutes.
You can manually unmount with umount ./content in Linux, and fusermount -u ./content in Mac OS.
To mount raw again, simply re-run the same command. This time it will only ask for the password.

## Limitations:
Limitations
encfs is not a standard command/package. Major Linux distros have it in their repos, on Mac OS you can install using ports. (sudo port install encfs)

