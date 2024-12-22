# Compare (diff) vim-generated backup of a file with that file's current version.

## Command:
```
$ diff~() { diff "$1"~ "$1"; }
```

## Explanation:
Explanation
When you save a file in vim, and you have the backup setting enabled, vim will save the previous version of the file as a separate file with the same name, but appending a ~ (tilde) character to the file name.  For example, if I have an existing file named test.txt, and I write changes to it, then vim will create the file test.txt~ with the previous contents of the file.
For developers it is often very useful to compare a file with the previous version by using the diff command.  For example: diff test.txt~ test.txt.  Sometimes file names can be long, and it can become tedious to have to enter the file name twice so many times.
The diff~ function saves you the trouble of entering the file name twice.  Following our example, we could invoke our function as diff~ test.txt.
Note that you can disable the backup setting in vim if you don't want to have these files created.  From within vim you can enter :set nobackup to disable, :set backup to enable, or :set backup? to see the current status.

## Limitations:
No limitations specified

