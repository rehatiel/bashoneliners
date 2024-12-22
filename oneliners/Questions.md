# Questions

## Command:
```
$ find . -name custlist\* | perl -ne '$path = $_; s?.*/??; $name = $_; $map{$name} = $path; ++$c; END { print $map{(sort(keys(%map)))[$c-1]} }'
```

## Explanation:
Explanation
The purpose of the one-liner is to find the the "latest" version of the custlist_*.xls file from among multiple versions in directories and sub-directories, for example:
./c/custlist_v1.003.xls
./c/custlist_v2.001.xls
./d/b/custlist_v1.001.xls
./d/custlist_v1.002.xls

Let's decompose the one-liner to the big steps:

find . -name custlist\* -- find the files matching the target pattern
... | perl -ne '...' -- run perl, with the input wrapped around in a while loop so that each line in the input is set in the variable $_
$path = $_; s?.*/??; $name = $_; -- save the full path in $path, and cut off the subdirectory part to get to the base name of the file and save it in $name
$map{$name} = $path; -- build a mapping of $name to $path
++$c; -- we count the elements, to use it later
(sort(keys(%map)))[$c-1] -- sort the keys of the map, and get the last element, which is custlist_v2.001.xls in this example
END { print $map{$last} }' -- at the end of all input data, print the path of the latest version of the file

## Limitations:
Limitations
Even if the latest version of the file appears multiple times in the directories, the one-liner will print only one of the paths. This could be fixed though if needed.

