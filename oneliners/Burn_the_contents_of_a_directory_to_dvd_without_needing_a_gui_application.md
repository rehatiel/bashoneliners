# Burn the contents of a directory to dvd without needing a gui application

## Command:
```
$ growisofs -dvd-compat -Z /dev/scd0 -R -J -pad /path/to/dir
```

## Explanation:
Explanation
Useful if you have a directory full of data to burn to DVD without using a GUI. 
The growisofs tool is in the "dvd+rw-tools" package in Ubuntu, install it with:
sudo apt-get install dvd+rw-tools

## Limitations:
No limitations specified

