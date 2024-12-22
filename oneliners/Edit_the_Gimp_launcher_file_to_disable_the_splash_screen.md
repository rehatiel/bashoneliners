# Edit the Gimp launcher file to disable the splash screen

## Command:
```
$ sudo sed -i 's/^Exec=[^ ]*/& -s/' /usr/share/applications/gimp.desktop
```

## Explanation:
Explanation

The -i flag of sed means to perform the command "in place", that is, save any changes in the input file. Use this flag with extreme caution, one wrong move and you can completely break the original file.
The regex pattern /^Exec=[^ ]*/ will match the line starting with Exec= followed by zero or more non-space characters.
In the replacement string, & -s, the & is replaced with whatever was matched, in this example probably something like Exec=gimp-2.8, after which we add a space and the -s flag which will effectively disable the splash screen when starting Gimp.

## Limitations:
Limitations
The -i flag of sed works differently in GNU and BSD systems. This example works in GNU systems only. The equivalent in BSD is:
sudo sed -i '' 's/^Exec=[^ ]*/& -s/' /usr/share/applications/gimp.desktop

In any case, always be very careful when using the -i flag of sed.

