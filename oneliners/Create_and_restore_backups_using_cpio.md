# Create and restore backups using cpio

## Command:
```
$ find . -xdev -print0 | cpio -oa0V | gzip > path_to_save.cpio.gz
```

## Explanation:
Explanation
To restore: 

gzip -cd path_to_save.cpio.gz | cpio -imV

Why not use tar instead? cpio is slightly more accurate!

find . -xdev -print0 finds all files and directories without crossing over to other partitions and prints a null delimited list of filenames
cpio -oa0V takes the list of files to archive from stdin and creates an archive file preserving timestamps and permissions
cpio -imV extracts the files and directories from stdin while preserving timestamps and permissions

## Limitations:
No limitations specified

