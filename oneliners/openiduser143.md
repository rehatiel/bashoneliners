# openiduser143

## Command:
```
$ sudo yum upgrade && for pkg in $(package-cleanup --orphans -q); do repoquery $(rpm -q $pkg --queryformat="%{NAME}") | grep -q ".*" && echo $pkg; done | xargs sudo yum -y remove && for pkg in $(package-cleanup --leaves --all -q); do repoquery --groupmember $pkg | grep -q "@" || echo $pkg; done
```

## Explanation:
Explanation
"sudo yum upgrade" does clean up outdated packages that the current upgrade replaces, but not other outdated packages or the ones that it willfully skips. Yes, that's what "package-cleanup --orphans" will finish, but "orphaned packages" also include packages that are at their latest version but just aren't updated by the repositories (usually a discrete .rpm installation). This one-liner uses "package-cleanup --orphans" but wraps around it to skip packages that aren't in the repositories anyway and just removes outdated packages that have a newer version in the repositories.
No, it's not at the end yet. It has a final command to display all packages that don't belong to any group. Choose any of the "manual extension" packages which aren't really necessary and only clog the system.

## Limitations:
Limitations

Specific to only rpm and yum
No, not just yum, it requires the yum-utils package (or whatever else provides package-cleanup and repoquery, if anything)

