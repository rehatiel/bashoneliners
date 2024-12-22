# Make a hexdump or do the reverse with the xxd command

## Command:
```
$ xxd /path/to/binary/file
```

## Explanation:
Explanation
This shows a very nice hexdump of the specified file. You can edit the output and convert it back to binary with xxd -r. But the best part is that you can configure vim to do all the converting back and forth for you, effectively turning vim into a binary editor, by adding this to your .vimrc:
augroup Binary
    au!
    au BufReadPre  *.bin let &bin=1
    au BufReadPost *.bin if &bin | %!xxd
    au BufReadPost *.bin set ft=xxd | endif
    au BufWritePre *.bin if &bin | %!xxd -r
    au BufWritePre *.bin endif
    au BufWritePost *.bin if &bin | %!xxd
    au BufWritePost *.bin set nomod | endif
augroup END

This will work for editing .bin files. To use it for other file extensions too, duplicate the lines within augroup and replace *.bin with *.exe for example.
This tip is from vim's :help xxd.

## Limitations:
No limitations specified

