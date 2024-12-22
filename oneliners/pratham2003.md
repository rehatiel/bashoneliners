# pratham2003

## Command:
```
$ cat post-list.csv | split -l 30 - --filter='jq -R . | jq --slurp -c .' | xargs -d "\n" -I % sh -c 'curl -H "Content-Type: application/json" -X POST -d '"'"'{"type":1,"entries":%}'"'"' http://127.0.0.1:8080/purge-something && sleep 30'
```

## Explanation:
Explanation
post-list.csv contains list of URLs in my example.


split -l 30 Split by 30 lines


- Use stdin as input for split


--filter Couldn't find a way to easily pipe to stdout from split, hence --filter


jq -R . From the jq manual - Don’t parse the input as JSON. Instead, each line of text is passed to the filter as a string


jq --slurp -c . From the jq manual - Instead of running the filter for each JSON object in the input, read the entire input stream into a large array and run the filter just once. -c makes it easier to pipe and use it in the xargs that follows.


xargs -d "\n" -I % sh -c Execute a command for each array. Use "\n" as delimiter. Use % as a placeholder in the command that follows.


Single quotes inside sh -c ' ... ' are escaped as '"'"' single-double-single-double-single. You can do whatever you need to inside sh -c ' ... && sleep 123'

## Limitations:
Limitations
You need jq installed, for example in Debian / Ubuntu:
apt-get install jq`

See also https://stedolan.github.io/jq/manual/
I suspect the input file (cat post-list.csv) may not contain double or single quotes but haven't tested it.

