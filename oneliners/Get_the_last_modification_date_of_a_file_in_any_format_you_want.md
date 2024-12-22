# Get the last modification date of a file in any format you want

## Command:
```
$ date -r /etc/motd +%Y%m%d_%H%M%S
```

## Explanation:
Explanation
The -r flag is a shortcut of --reference and it is used to specify a reference file. Used in this way, the date command prints the last modification date of the specified file, instead of the current date.
The + controls the output format, for example:

%Y = 4-digit year
%m = 2-digit month
%d = 2-digit day
%H = 2-digit hour
%M = 2-digit minutes
%S = 2-digit seconds

So in this example +%Y%m%d_%H%M%S becomes 20121001_171233
You should be able to  find all the possible format specifiers in man date.

## Limitations:
Limitations
The default date command in Solaris does not support the --reference flag. Modern Solaris systems have the GNU tools installed, so you may be able to find the GNU implementation of date which supports this flag. Look for it in /usr/gnu/bin/date or /usr/local/bin/date, or do search the entire /usr with find /usr -name date. 
In Solaris this may be a suitable substitute without using the date command:
ls -Ego /etc/motd | awk '{print $4 "_" $5}' | tr -d :- | sed -e 's/\..*//'

Or you can use good old perl:
perl -mPOSIX -e 'print POSIX::strftime("%Y%m%d_%H%M%S\n", localtime((stat("/etc/motd"))[9]))'

