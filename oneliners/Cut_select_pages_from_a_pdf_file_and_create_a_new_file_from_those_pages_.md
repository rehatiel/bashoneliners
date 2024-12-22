# Cut select pages from a pdf file and create a new file from those pages.

## Command:
```
$  pdftk input.pdf cat 2-4 7 9-10 output output.pdf
```

## Explanation:
Explanation
pdftk is the PDF Toolkit 
input.pdf is the input file.
cat 2-4 7 9-10 concatenate (combine) pages 2,3,4,7,9,10 of input.pdf.
output output.pdf the resulting pdf file containing the above pages.

## Limitations:
Limitations
Only a single contiguous range of pages can be specified.

