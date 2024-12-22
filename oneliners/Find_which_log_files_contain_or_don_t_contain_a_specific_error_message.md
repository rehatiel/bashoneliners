# Find which log files contain or don't contain a specific error message

## Command:
```
$ for i in *.log; do grep OutOfMemo $i >/dev/null && echo $i oom || echo $i ok; done
```

## Explanation:
Explanation
In this example I was looking for a list of log files which contain or don't contain a stack trace of OutOfMemoryError events.

for i in *.log is to loop over the list of files.
For each file, I run grep, but redirect the output to /dev/null, as I don't need that, I just want to see a "yes or no" kind of summary for each file
grep exits with success if it found any matching lines, otherwise with failure. Using the pattern cmd && success || failure, I echo the filename and the text "oom" in case of a match, or "ok" otherwise

Remarks:

Using grep -q is equivalent to redirecting output to /dev/null, but might not be supported in all systems
grep -l can be used to list files with matches, and grep -L to list files without matches, but the latter does not exist in some implementations of grep, such as BSD
I realized it a bit late, but grep -c shows a count of the matches, so actually it could have been a suitable and simpler solution

## Limitations:
No limitations specified

