# Test git archive before actually creating an archive // fake dry run

## Command:
```
$ git archive master some/project/subdir | tar t
```

## Explanation:
Explanation
git archive doesn't have a --dry-run flag, and it would be nice to see what files would be in the archive before actually creating it.

git archive master some/project/subdir
Create an archive from the master branch, with only a specified sub-directory of the project in it (instead of the entire repo)
Note: without specifying a file, the archive is dumped to standard output
tar t : the t flag of tar is to list the content of an archive. In this example the content comes from standard input (piped from the previous command)

In other words, this command creates an archive without ever saving it in a file, and uses tar t to list the contents. If the output looks good, then you can create the archive with:
git archive master -o file.tar some/project/subdir

## Limitations:
No limitations specified

