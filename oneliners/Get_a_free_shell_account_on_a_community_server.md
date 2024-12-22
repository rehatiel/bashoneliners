# Get a free shell account on a community server

## Command:
```
$ sh <(curl hashbang.sh | gpg)
```

## Explanation:
Explanation
Bash process substitution which curls the website 'hashbang.sh'  and executes the shell script embedded in the page.
This is obviously not the most secure way to run something like this, and we will scold you if you try.
The smarter way would be:
Download locally over SSL
curl https://hashbang.sh >> hashbang.sh

Verify integrity with GPG (if available):
gpg --recv-keys 0xD2C4C74D8FAA96F5
gpg --verify hashbang.sh

Inspect source code:
less hashbang.sh

Run:
chmod +x hashbang.sh
./hashbang.sh

## Limitations:
No limitations specified

