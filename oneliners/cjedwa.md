# cjedwa

## Command:
```
$ unless => "client_remote=\"$(curl localhost:9200/_cluster/settings | python -c \"import json,sys;obj=json.load(sys.stdin);print(obj['persistent']['search']['remote'])\")\"; new_remote=\"$( echo $persistent_json | python -c \"import json,sys;obj=json.load(sys.stdin);print(obj['persistent']['search']['remote'])\")\"; [ \"$client_remote\" = \"$new_remote\" ]",
```

## Explanation:
No explanation available

## Limitations:
No limitations specified

