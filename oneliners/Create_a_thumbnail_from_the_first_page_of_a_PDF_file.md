# Create a thumbnail from the first page of a PDF file

## Command:
```
$ convert -thumbnail x80 file.pdf[0] thumb.png
```

## Explanation:
Explanation

convert is part of ImageMagick image manipulation tool
-thumbnail x80 means create a thumbnail image of height 80 pixels, the width will be automatically chosen to make the image proportional
The [0] is to create a thumbnail for the first page only, without that a thumbnail image would be created for each page in the pdf file

To do this for all PDF files in a directory tree:
find /path/to/dir -name '*.pdf' -exec convert -thumbnail x80 {}[0] {}-thumb.png \;

## Limitations:
Limitations
Requires the ImageMagick image manipulation tool.

