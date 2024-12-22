# Find the most recently modified files in a directory and all subdirectories

## Command:
```
$ find /path/to/dir -type f | perl -ne 'chomp(@files = <>); my $p = 9; foreach my $f (sort { (stat($a))[$p] <=> (stat($b))[$p] } @files) { print scalar localtime((stat($f))[$p]), "\t", $f, "\n" }' | tail
```

## Explanation:
Explanation

find path_to_dir -type f prints all the files in the directory tree
chomp(@files = <>); reads all the lines into an array
stat($a) is an array of interesting info about a file. Index 7 is size, 8 is access time, 9 is modification time, etc. (See man perlfunc for details and search for stat EXPR.)
sort { (stat($a))[9] <=> (stat($b))[9] } @files sorts the files by modification time
print scalar localtime((stat($f))[9]), "\t", $f, "\n" - prints the modification time formatted nicely, followed by a tab and the filename

## Limitations:
No limitations specified

