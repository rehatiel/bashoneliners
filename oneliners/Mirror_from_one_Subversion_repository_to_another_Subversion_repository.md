# Mirror from one Subversion repository to another Subversion repository

## Command:
```
$ bzr co https://repo1/proj1/trunk proj1 && cd proj1 && bzr push https://repo2/vendor/proj1/trunk
```

## Explanation:
Explanation

The commit history in repo1 will be copied to repo2.
The temporary Bazaar repository (proj1) will have the full history of changes.
The command above initializes the mirror. To update the mirror, run this script, you can schedule it to run periodically to keep the mirror up to date:
cd proj1 && bzr up && bzr push

## Limitations:
Limitations

The author information will get lost in the process.

