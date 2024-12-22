# Repeat the previous command but with a string replacement

## Command:
```
$ ^geomtry^geometry
```

## Explanation:
Explanation
This can be very useful for example after a mistyped command like this:
convert -crop 745x845+0+150 my_logo.png -geomtry 400x my_logo2.png
^geomtry^geometry

"-geomtry" should have been "-geometry", the one-liner above will re-run the command with a replacement that fixes the typo.

## Limitations:
No limitations specified

