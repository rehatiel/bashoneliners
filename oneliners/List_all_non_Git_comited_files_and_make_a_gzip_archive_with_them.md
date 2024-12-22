# List all non Git comited files and make a gzip archive with them

## Command:
```
$ GITFOLDER="/srv/some/folder"   ls-files --others --exclude-standard | tar czf ${GITFOLDER}-archives/uploads-$(date '+%Y%m%d%H%M').tar.gz -T -
```

## Explanation:
Explanation
Assuming your web app has a git checkout is in /srv/some/folder (i.e. there is a /srv/some/folder/.git), archive the user uploads to /srv/some/folder-archives with that one liner.
Use:
cd /srv/some/folder
# this one-liner

## Limitations:
Limitations
A fully complete script would:

Check if $GITFOLDER exists
Check if $GITFOLDER has a .git directory
Create a temporary (e.g. tmp=$(mktemp)) file to log anything; if [ "$?" -ne 0 ] ; exit with status exit 1, otherwise delete the $tmp file and exit 0.

