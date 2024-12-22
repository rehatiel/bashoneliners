# List the content of a GitHub repository without cloning it

## Command:
```
$ svn ls https://github.com/user/repo/trunk/some/path
```

## Explanation:
Explanation
Git doesn't allow querying sub-directories of a repository. But GitHub repositories are also exposed as Subversion repositories, and Subversion allows arbitrary path queries using the ls command.
Notice the /trunk/ between the base URL of the repository and the path to query. This is due to the way GitHub provides Subversion using a standard Subversion repository layout, with trunk, branches and tags sub-directories.

## Limitations:
No limitations specified

