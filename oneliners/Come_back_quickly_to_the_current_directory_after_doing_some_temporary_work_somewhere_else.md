# Come back quickly to the current directory after doing some temporary work somewhere else

## Command:
```
$ pushd /some/where/else; work; cd /somewhere; work; cd /another/place; popd
```

## Explanation:
Explanation

pushd, popd and dirs are bash builtins, you can read about them with help dirs
bash keeps a stack of "remembered" directories, and this stack can be manipulated with the pushd and popd builtins, and displayed with the dirs builtin
pushd will put the current directory on top of the directory stack. So, if you need to change to a different directory temporarily and you know that eventually you will want to come back to where you are, it is better to change directory with pushd instead of cd. While working on the temporary task you can change directories with cd several times, and in the end when you want to come back to where you started from, you can simply do popd.

## Limitations:
No limitations specified

