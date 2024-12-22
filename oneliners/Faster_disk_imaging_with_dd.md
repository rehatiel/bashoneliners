# Faster disk imaging with dd

## Command:
```
$ dd if=/dev/sda bs=$(hdparm -i /dev/sda | grep BuffSize | cut -d ' ' -f 3 | tr [:lower:] [:upper:] | tr -d BUFFSIZE=,) conv=noerror | dd of=image.dd conv=noerror
```

## Explanation:
Explanation
GNU dd (disk dump) copies any block device to another block device or file. It's really useful for disk cloning, but its usual invocation isn't as fast as it could be. These settings, or settings like them, often improve copying speed by more than double.

Piping the input of dd into the output of another instance seems to always improve copying speed.
/dev/sda refers to your input device, which may vary. Check yours with fdisk -l.
image.dd refers to the copy stored in the current working directory. You can also use another block device, such as /dev/sdb. WARNING! Be sure you know what you set the output file to! A mistake here could do irreparable damage to your system.
The entire hdparm subshell sets dd's input block size to the buffer size of the source medium. This also usually improves copy speed, but may need adjustment (see limitations below).
conv=noerror tells dd to ignore read errors.

Check dd's progress with:
kill -USR1 $(pidof dd)

## Limitations:
Limitations
The hdparm subshell is not appropriate for block devices without buffers, like flash drives. Try block sizes from 512 bytes to 1 or 2MiB to get the best speed.
 dd usually requires root privileges to run, because it is very powerful and dangerous, and will not prompt when overwriting!. If you're not careful where dd outputs, you may permanently destroy all or part of your system. Use with care; double-check all parameters, especially the of file/device!

