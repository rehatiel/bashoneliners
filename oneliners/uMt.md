# uMt

## Command:
```
$ find ~ -name ".git" 2> /dev/null | sed 's/\/.git/\//g' | awk '{print "-------------------------\n\033[1;32mGit Repo:\033[0m " $1; system("git --git-dir="$1".git --work-tree="$1" status")}'
```

## Explanation:
Explanation

List all .git dirs
Trim .git parts
Run git --git-dir=X.git --work-tree=X status with awk

## Limitations:
No limitations specified

