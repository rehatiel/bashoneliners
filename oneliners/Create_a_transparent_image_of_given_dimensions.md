# Create a transparent image of given dimensions

## Command:
```
$ convert -size 100x100 xc:none transparency.png
```

## Explanation:
Explanation

convert is a tool that's part of the ImageMagick image manipulation library
-size 100x100 specifies the dimensions of the image to create
xc:none is a symbolic source image, indicating to convert "from nothing"
transparency.png is the destination filename, the image format is automatically determined by the extension

## Limitations:
Limitations
Requires the ImageMagick image manipulation library.

