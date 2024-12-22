# Store the output of find in an array

## Command:
```
$ mapfile -d $'\0' arr < <(find /path/to -print0)
```

## Explanation:
Explanation
mapfile (also known as readarray) reads lines from the standard input an array variable.
-d is to specify a line delimiter instead of the default newline. Here we used $'\0', which means ASCII NUL character (character code 0), to match with -print0 used with find. It's clear that the delimiter used by find and mapfile must match for the command to make sense. Using the null character is a good idea, because it can never appear in UNIX filenames.
It's crucial that mapfile reads the content from a process substitution with < <(...), and not from a pipe. This will NOT work:

find /path/to -print0 | mapfile -d $'\0' arr


The above will not work, because commands in a pipeline run in a sub-shell, and as such arr would not be visible after the pipeline terminates. This is a key piece that the process substitution solves, by running in the current process.
Finally, an example to loop over the contents of arr safely:
for path in "${arr[@]}"; do ...; done

## Limitations:
Limitations
mapfile and readarray are features of Bash 4.

