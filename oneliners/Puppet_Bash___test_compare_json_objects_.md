# Puppet/Bash:  test compare json objects.

## Command:
```
$ unless => "client_remote=\"$(curl localhost:9200/_cluster/settings | python -c \"import json,sys;obj=json.load(sys.stdin);print(obj['persistent']['search']['remote'])\")\"; new_remote=\"$( echo $persistent_json | python -c \"import json,sys;obj=json.load(sys.stdin);print(obj['persistent']['search']['remote'])\")\"; [ \"$client_remote\" = \"$new_remote\" ]",
```

## Explanation:
Explanation
One json object provided by puppet dictionary the other grabbed from Elasticsearch rest API. Only run command if these don't match. Had issues getting jq to sort properly so used python.

## Limitations:
No limitations specified

