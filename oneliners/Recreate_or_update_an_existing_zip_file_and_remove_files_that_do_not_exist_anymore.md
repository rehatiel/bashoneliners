# Recreate or update an existing zip file and remove files that do not exist anymore

## Command:
```
$ zip --filesync -r /path/to/out.zip /path/to/dir
```

## Explanation:
Explanation
zip does not have an explicit option to overwrite/recreate an existing zip file. If the specified destination file already exists, zip updates it. The problem is that files you did not specify to add to the zip but they already existed in the zip, will not be removed.
For example let's say you created a zip file from a directory with the command:
zip -r /path/to/out.zip /path/to/dir

Next you delete some files from the directory and repeat the command to recreate the zip. But that will not recreate the zip, it will only update it, and so the file you deleted from the directory will still be there in the zip.
One way to recreate the zip is to delete the file first. Another, better way is to use the --filesync or -FS flag. With this flag zip will remove files from the zip that do not exist anymore in the filesystem. This is more efficient than recreating the zip.

## Limitations:
No limitations specified

