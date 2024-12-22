# Anon6y5E4Use

## Command:
```
$ GZIP='--rsyncable' tar cvzf bobsbackup.tar.gz /home/bob
```

## Explanation:
Explanation
rsync works by comparing files on the local and remote machine and only sending those parts of the file that have changed.  The normal way compression works, it results in everything after the modification changing, meaning lots of data ends up going over the network when you try to rsync compressed files.
The --rsyncable option to gzip changes the compression scheme so that modifications to the input file only affect the part of the file where they're located.  This allows rsync to work its magic.
In this one-liner, the z option to tar calls gzip, which recognizes and uses any options specified in the GZIP environment variable.

## Limitations:
Limitations
Using the --rsyncable option results in a slightly larger compressed file.
Not all versions of gzip include this feature - use the --help option to see if it's available on your system.

