# Rename files with numeric padding

## Command:
```
$ perl -e 'for (@ARGV) { $o = $_; s/\d+/sprintf("%04d", $&)/e; print qq{mv "$o" "$_"\n}}'
```

## Explanation:
Explanation
Basically a one-liner perl script. Specify the files to rename as command line parameters, for example:
perl -e '.....' file1.jpg file2.jpg

In this example the files will be renamed to file0001.jpg and file0002.jpg, respectively. The script does not actually rename anything. It only prints the shell commands to execute that would perform the renaming. This way you can check first that the script would do, and if you want to actually do it, then pipe the output to sh like this:
perl -e '.....' file1.jpg file2.jpg | sh

What's happening in the one-liner perl script:

for (@ARGV) { ... } is a loop, where each command line argument is substituted into the auto-variable $_. 
$o = $_ :: save the original filename
s/// :: perform pattern matching and replacement on $_
print qq{...} :: print the mv command, with correctly quoted arguments

## Limitations:
Limitations
The script does not cover all corner cases. For example it will not work with files that have double-quotes in their names. In any case, it is safe to review the output of the script first before piping it to sh.
If your system has the rename command (Linux), then a shortcut to do the exact same thing is with:
rename 's/\d+/sprintf("%04d", $&)/e' *.jpg

It handles special characters better too.

