# Use ghostscript to shrink PDF files

## Command:
```
$ gs -sDEVICE=pdfwrite -dCompatibilityLevel=1.4 -dPDFSETTINGS=/ebook -dNOPAUSE -dQUIET -dBATCH -sOutputFile=output.pdf input.pdf
```

## Explanation:
Explanation
Replace input.pdf and output.pdf with the original PDF name and the new compressed version's file name respectively.  The key to this is the PDFSETTINGS option which can be tuned for various levels of compression.  For scanned text documents, I find the ebook setting works well enough for most purposes but you can experiment with the options below.

-dPDFSETTINGS=/screen (screen-view-only quality, 72 dpi images)
-dPDFSETTINGS=/ebook (low quality, 150 dpi images)
-dPDFSETTINGS=/printer (high quality, 300 dpi images)
-dPDFSETTINGS=/prepress (high quality, color preserving, 300 dpi imgs)
'-dPDFSETTINGS=/default (almost identical to /screen)'

## Limitations:
No limitations specified

