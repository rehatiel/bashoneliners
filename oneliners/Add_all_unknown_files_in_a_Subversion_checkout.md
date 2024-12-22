# Add all unknown files in a Subversion checkout

## Command:
```
$ svn add . --force
```

## Explanation:
Explanation
Adding all unknown files in a working tree is usually very simple in other version control systems, for example:
git add .
bzr add

Not so simple in Subversion:
$ svn add .
svn: warning: '.' is already under version control

But if you add the --force flag, that will do!
Keep in mind that this is not the same as:
svn add * --force

That would add not only unknown files, but ignored files too, which is probably not your intention. Make sure to specify directories explicitly, avoid using * with this command.

## Limitations:
No limitations specified

