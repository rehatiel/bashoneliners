# Alert me by email when a disconnected or unreachable server comes back online

## Command:
```
$ while ! ping -c1 the_host_down; do sleep 1; done && date | mail -s 'the host is back!' me@example.com
```

## Explanation:
Explanation

ping -c1 host sends just one ping and exits with success or error.
while will keep running until the ping succeeds
When the ping succeeds the while loop will end, and an email will be sent with the date as the message

## Limitations:
Limitations

Depending on your system the parameter for sending a single ping might be different from -c1
Depending on your system the mail command might be different or work differently

