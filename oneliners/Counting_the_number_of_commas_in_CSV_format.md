# Counting the number of commas in CSV format

## Command:
```
$ perl -ne 'print tr/,//, "\n"' < file.csv | sort -u
```

## Explanation:
Explanation
Sometimes I need to know if a CSV file has the right number of columns, and how many columns there are.
The tr/// operator in perl is normally used to convert a set of characters to another set of characters, but when used in a scalar context like in this example, it returns the number of matches of the specified characters, in this case a comma.
The perl command above prints the number of commas in every line of the input file. sort -u sorts this and outputs only the unique lines. If all lines in the CSV file have the same number of commas, there should be one line of output. The number of columns in the file is this number + 1.

## Limitations:
Limitations
This one-liner does not handle the more general case when the columns may have embedded commas within quotes. For that you would need a more sophisticated method. This simple version can still be very useful in many common cases.

