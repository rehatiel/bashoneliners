# md5sum the last 5 files in a folder

## Command:
```
$ find /directory1/directory2/ -maxdepth 1 -type f | sort | tail -n 5 | xargs md5sum
```

## Explanation:
Explanation

find lists the files, no recursion, no directories, with full path
sort list files alphabetically
tail keep only the last 5 files
xargs send the list as arguments to md5sum
md5sum calculate the md5sum for each file

## Limitations:
Limitations
Probably can't handle spaces in file or directory names.

