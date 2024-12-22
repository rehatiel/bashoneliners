# kowalcj0

## Command:
```
$ md5sum <<< YOUR_TEXT | cut -f1 -d' '
```

## Explanation:
Explanation
Calculate a MD5 sum/digest from an input string
Wrap it up in a function:
function md5() { md5sum <<< $1 | cut -f1 -d' '; }

Example usage:
md5 "this is a long string test_string"
md5 singleWordExample

## Limitations:
No limitations specified

