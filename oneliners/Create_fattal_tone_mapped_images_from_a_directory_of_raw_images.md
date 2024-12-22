# Create fattal tone mapped images from a directory of raw images

## Command:
```
$ for img in /path/to/rawimages/*.RW2; do pfsin ${img} | pfssize -x 1024 -y 768 | pfstmo_fattal02 -v -s 1 | pfsout /path/to/finished/${img%%}.jpg; done
```

## Explanation:
Explanation
for img in /path/to/rawimages/*.RW2; do Loop through image directory
pfsin ${img} | read the raw image
pfssize -x 1024 -y 768 | resize it to 1024x768 because fattal looks better at low resolutions
pfstmo_fattal02 -v -s 1 | use the fattal tone mapping operator, be verbose and saturation value of 1
pfsout ./path/to/finished/${img%%}.jpg; done output and rename the file as a jpg.
Examples of fattal tone mapped images http://goo.gl/IayQQ
pfstools website http://pfstools.sourceforge.net/

## Limitations:
Limitations
Portrait orientation images need to be processed -x 768 -y 1024

