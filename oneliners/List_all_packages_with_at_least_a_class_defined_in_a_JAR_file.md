# List all packages with at least a class defined in a JAR file

## Command:
```
$ jar tf "$1" | grep '/.*\.class$' | xargs dirname | sort -u | tr / .
```

## Explanation:
Explanation
The jar command allows you to read or manipulate JAR (Java ARchive) files, which are ZIP files that usually contain classfiles (Java compiled bytecode files) and possibly manifests and configuration files. We specify that we want to list file contents (t) that we provide as an argument (f, otherwise the jar will be read from stdin).
From the output, we get only the paths that contain a classfile (grep), then the path to the package that contains it (xargs dirname), we get the unique, sorted paths and translate /s to .s (to display their names as they would be shown in Java syntax).

## Limitations:
Limitations
Will only exhaustively list the packages with a defined class for languages that require packages to map to the directory structure (e.g.: Java does, Scala doesn't). If this convention is respected, the command will output an exhaustive list of packages nonetheless.

