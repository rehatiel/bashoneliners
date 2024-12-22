
# Rename all files in a directory to lowercase names

### Command:
```bash
paste <(ls) <(ls | tr A-Z a-z) | while read OLD NEW; do echo mv -v $OLD $NEW; done
```

### Explanation:
- `<(cmd)` is the filename of a named pipe (FIFO), where the named pipe is filled by the output of `cmd`.
- `paste` puts together the named pipes to form two columns:
  - First column with the original filenames.
  - Second column with the lowercased filenames.
- `tr abc ABC` transforms stdin by replacing any characters that appear in the first set of letters to the second set of letters.
- `while read old new; do ...; done` reads each line, storing the first column into `$old` and the second column into `$new`.

### Limitations:
- Won't work if there are spaces in a filename.

---

### Alternative Command:
```bash
for i in *; do mv "$i" "${i,,}"; done
```

### Explanation:
- Loops over the items in the current directory.
- Uses Bash built-in case modification expansion to convert to lowercase.

### Limitations:
- The case modification extension is available since Bash 4.
