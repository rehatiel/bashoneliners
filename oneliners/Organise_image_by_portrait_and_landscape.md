# Organise image by portrait and landscape

## Command:
```
$ mkdir "portraits"; mkdir "landscapes"; for f in ./*.jpg; do WIDTH=$(identify -format "%w" "$f")> /dev/null; HEIGHT=$(identify -format "%h" "$f")> /dev/null; if [[ "$HEIGHT" > "$WIDTH" ]]; then mv "$f" portraits/ ; else mv "$f" landscapes/ ; fi; done
```

## Explanation:
Explanation

First makes directory for portraits and landscapes
Loops through all files in the current directory with the extention .jpg, feel free to change this to .png or .jpeg if neccesary
Gets the width and height for the current image using the identify command
If height > width, move it to Portarits folder, otherwise move it to landscapes

## Limitations:
Limitations
This relies on the identify command which comes with ImageMagick which is available on most systems.
This does not check for square images, although it could be easily extended to see if HEIGHT and WIDTH are equal. Square images are currently put with the landscape images.

