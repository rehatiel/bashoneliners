# dump network traffic with tcpdump to file with time-stamp in its filename

## Command:
```
$ date +"%Y-%m-%d_%H-%M-%Z" | xargs -I {} bash -c "sudo tcpdump -nq -s 0 -i eth0 -w ./dump-{}.pcap"
```

## Explanation:
Explanation
will dump the traffic into a file with a time-stamp in its name. Example filename:
dump-2013-05-17_15-46-UTC.pcap

## Limitations:
No limitations specified

