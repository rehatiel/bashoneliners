# Convert a list of terms in slug format to capitalized words

## Command:
```
$ sed -e 's/^./\U&/' -e 's/_./\U&/g' -e 's/_/ /g' /path/to/input
```

## Explanation:
Explanation
The goal here is to take an input like this:
police_station
post_office
real_estate_agency

... and convert it to an output like this:
Police Station
Post Office
Real Estate Agency


-e ... the sed command can take several -e parameters, which will be executed one by one when processing each line in the input
The s/// command is a pattern replacement, and has the general format s/pattern/replacement/flags
s/^./\U&/ - replace the first letter of the line with uppercase version of the letter: \U means convert to uppercase, & is the matched string
s/_./\U&/g- replace _ and any letter followed by it. The g flag at the end means a "global" replacement, so all occurrences of the pattern _. will be replaced
s/_/ /g - replace all underscores with spaces
Input to sed can come from a list of files, or input redirection with <, or from a pipe.

## Limitations:
No limitations specified

