# Create an encrypted tar file with openssl

## Command:
```
$ tar c paths_to_files_and_dirs | gzip -c | openssl des3 > encrypted.tar.gz
```

## Explanation:
Explanation
Decrypt with: openssl des3 -d < encrypted.tar.gz | tar zx

## Limitations:
No limitations specified

