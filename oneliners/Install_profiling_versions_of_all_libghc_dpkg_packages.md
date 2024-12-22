# Install profiling versions of all libghc dpkg packages

## Command:
```
$ sudo dpkg -l | grep libghc | grep "\-dev" | cut -d " " -f 3 | tr '\n' ' ' | sed -e 's/\-dev/\-prof/g' | xargs sudo apt-get install --yes
```

## Explanation:
Explanation
dpkg -l lists all installed system packages.
grep libghc filters out all haskell packages
grep "\-dev" filters out the actual source packages, where -dev can be replaced with -prof to get the name of the profiling package
cut -d " " -f 3 converts lines from ii  libghc-packagename-dev                                             0.1.3.3-7                                           amd64        description
to libghc-packagename-dev
tr '\n' ' ' Replaces newlines with spaces, merging it all into one line
sed -e 's/\-dev/\-prof/g' Replaces -dev with -prof
xargs sudo apt-get install --yes Passes the string (now looking like libghc-a-prof libghc-b-prof libghc-c-prof) as arguments to sudo apt-get install --yes which installs all package names it receives as arguments, and does not ask for confirmation.

## Limitations:
Limitations
Only works with apt (standard in ubuntu)

