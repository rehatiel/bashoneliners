# Convert pip list --outdated for reuse in pip install -U

## Command:
```
$ python3 -m pip install -U $(python3 -m pip list outdated 2> /dev/null | grep -v 'Version' | grep -v '\-\-\-\-\-\-' | awk '{printf $1 " " }' && echo)
```

## Explanation:
Explanation
I find it annoying that I have to cut & paste individual packages to 'pip install -U PACKAGE_NAMES...' to upgrade all python packages in a specific python installation.

## Limitations:
Limitations
This pip one-liner does not cover the outdated python 2 and the simple pip install -U in virtual environments .venv, but can relatively easily be adjusted to these different use cases.

