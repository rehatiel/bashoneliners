# Remove files and directories whose name is a timestamp older than a certain time

## Command:
```
$ ls | grep '....-..-..-......' | xargs -I {} bash -c "[[ x{} < x$(date -d '3 days ago' +%Y-%m-%d-%H%M%S) ]] && rm -rfv {}"
```

## Explanation:
Explanation
Suppose you have a backup directory with backup snapshots named by timestamp:
$ ls
2013-05-03-103022
2013-05-04-103033
2013-05-05-103023
2013-05-06-103040
2013-05-07-103022

You want to remove snapshots older than 3 days. The one-liner does it:
$ date
Tue May  7 13:50:57 KST 2013
$ ls | grep '....-..-..-......' | sort | xargs -I {} bash -c "[[ x{} < x$(date -d '3 days ago' +%Y-%m-%d-%H%M%S) ]] && rm -rfv {}"
removed directory: `2013-05-03-103022'
removed directory: `2013-05-04-103033'

## Limitations:
Limitations
It doesn't work on OS X due to the differences between GNU date and BSD date).

