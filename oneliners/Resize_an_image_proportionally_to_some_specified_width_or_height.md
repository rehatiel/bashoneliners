# Resize an image proportionally to some specified width or height

## Command:
```
$ mogrify -geometry x31 path/to/image.gif
```

## Explanation:
Explanation

mogrify is part of ImageMagick, an image manipulation software suite
mogrify manipulates the specified images. If you prefer to keep the original image untouched and write the manipulated image to a different file, simply replace mogrify with convert, the syntax is the same, but the last command line argument will be the target image to write to.
The -geometry flag is to resize the image, it requires a dimension parameter in the format WIDTHxHEIGHT
The dimension in this example has no width, which means the image will be resized to height=31 pixels, and the width will be proportional.

## Limitations:
Limitations
ImageMagick is not a standard package, though it is open source and available in many systems.

