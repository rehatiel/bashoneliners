# Go up to a particular folder

## Command:
```
$ alias ph='cd ${PWD%/public_html*}/public_html'
```

## Explanation:
Explanation
I work on a lot of websites and often need to go up to the public_html folder.
This command creates an alias so that however many folders deep I am, I will be taken up to the correct folder.
alias ph='....': This creates a shortcut so that when command ph is typed, the part between the quotes is executed
cd ...: This changes directory to the directory specified
PWD: This is a global bash variable that contains the current directory
${...%/public_html*}: This removes /public_html and anything after it from the specified string
Finally, /public_html at the end is appended onto the string.
So, to sum up, when ph is run, we ask bash to change the directory to the current working directory with anything after public_html removed.
Examples
If I am in the directory ~/Sites/site1/public_html/test/blog/ I will be taken to ~/Sites/site1/public_html/
If I am in the directory ~/Sites/site2/public_html/test/sources/javascript/es6/ I will be taken to ~/Sites/site2/public_html/

## Limitations:
No limitations specified

