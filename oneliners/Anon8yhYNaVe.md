# Anon8yhYNaVe

## Command:
```
$ printf '%s\n' ',s/^Exec=[^ ]*/& -s/' w q | ed /usr/share/applications/gimp.desktop
```

## Explanation:
Explanation
sed is designed for editing streams - editing files is what ed is for!  You can get consistent behavior on any UNIX platform with the above one-liner.
The printf command sends a series of editing commands to ed, each separated by a newline.  In this case, the substitution command ,s/^Exec=[^ ]*/& -s/ is nearly the same as in sed, appending a space and a -s to the line starting with Exec=.  The only difference is the comma at the beginning designating the lines to operate on.  This is shorthand for 1,$, which tells ed to apply the command to the first through the last lines (i.e., the entire file).  w tells ed to write the file, and q to quit.

## Limitations:
Limitations
The -i flag of sed works differently in GNU and BSD systems. This example works in GNU systems only. The equivalent in BSD is:
sudo sed -i '' 's/^Exec=[^ ]*/& -s/' /usr/share/applications/gimp.desktop

In any case, always be very careful when using the -i flag of sed.

