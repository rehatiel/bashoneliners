# Replace sequences of the same characters with a single character

## Command:
```
$ echo heeeeeeelllo | sed 's/\(.\)\1\+/\1/g'
```

## Explanation:
Explanation
That is, this will output "helo".
The interesting thing here is the regular expression in the s/// command of sed:

\(.\) -- capture any character
\1 -- refers to the last captured string, in our case the previous character. So effectively, \(.\)\1 matches pairs of the same character, for example aa, bb, ??, and so on.
\+ -- match one or more of the pattern right before it
... and we replace what we matched with \1, the last captured string, which is the first letter in a sequence like aaaa, or bbbbbbb, or cc.

## Limitations:
No limitations specified

