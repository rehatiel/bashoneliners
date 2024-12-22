# Remove EXIF data such as orientation from images

## Command:
```
$ mogrify -strip /path/to/image.jpg
```

## Explanation:
Explanation
I use this mostly to remove orientation information from images. My problem with orientation information is that some viewers don't support it, and thus do not show the image correctly oriented. Rotating the image doesn't help, because if I make the image look correct in the viewer that doesn't support orientation, that will break it in the viewer that does support orientation. The solution is to remove the orientation information and rotate the image appropriately. That way the image will always look the same in all viewers, regardless of support for the orientation information.
The tool mogrify is part of ImageMagick, an image manipulation software. It manipulates image files and saves the result in the same file. A similar tool in ImageMagick that saves the result of manipulations is convert, you can use it like this:
convert -strip orig.jpg stripped.jpg

## Limitations:
Limitations
The tool is part of ImageMagick, an image manipulation software.

