# olshek_

## Command:
```
$ echo "address=/ru/0.0.0.0" | sudo tee /etc/NetworkManager/dnsmasq.d/dnsmasq-ru-blackhole.conf && sudo systemctl restart network-manager
```

## Explanation:
Explanation
It creates dnsmasq-ru-blackhole.conf file with one line to route all domains of ru zone to 0.0.0.0.
You might use "address=/home.lab/127.0.0.1" to point allpossiblesubdomains.home.lab to your localhost or some other IP in a cloud.

## Limitations:
No limitations specified

