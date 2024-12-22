# ratfink417

## Command:
```
$ [[ $(sha256sum _downloaded_file_ | cut -d' ' -f 1) == $(grep -Po '\b[a-zA-Z0-9]{64}\b' _checksum_fle_) ]] && printf "\033[0;32mGood" || printf "\033[0;31mBad"
```

## Explanation:
No explanation available

## Limitations:
No limitations specified

