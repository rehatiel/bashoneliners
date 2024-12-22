# Re-compress a gzip (.gz) file to a bzip2 (.bz2) file

## Command:
```
$ time gzip -cd file1.tar.gz 2>~/logfile.txt | pv -t -r -b -W -i 5 -B 8M | bzip2 > file1.tar.bz2 2>>~/logfile .txt
```

## Explanation:
Explanation
*Requires PV (pipe viewer) if you want to monitor throughput; otherwise you can leave out the pv pipe.
Transparently decompresses an arbitrary .gz file (does not have to be a tar) and re-compresses it to bzip2, which has better compression and error recovery.  Echoes error messages to a file named logfile.txt in your home directory.
NOTE: The original .gz file will NOT be deleted.  If you want to save space, you will have to delete it manually.

## Limitations:
No limitations specified

