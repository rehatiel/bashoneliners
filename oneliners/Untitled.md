# Untitled

## Command:
```
sudo -s <<< 'apt update -y && apt upgrade -y'
```

## Explanation:
sudo -s executes in interactive shell, rather than a single command
With <<< '...' we redirect the content of '...' as input. The idiom <<<word is called a here string, for more details see man bash, search for "Here Strings".
apt update -y && apt upgrade -y is just an example of two commands chained with &&: first run apt update -y, and only if that is successful, then run apt upgrade -y.

This is different from simply running:
sudo apt update -y && apt upgrade -y

Because in this formulation only the first command (apt update -y) will run with sudo, the second command will run as a regular user.

## Limitations:
No limitations specified

