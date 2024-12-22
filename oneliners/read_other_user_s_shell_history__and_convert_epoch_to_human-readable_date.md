# read other user's shell history, and convert epoch to human-readable date

## Command:
```
$ cat /home/john/.bash_history | awk '/#[0-9]*$/ {split($0, arr, "#"); print "#", strftime("%c",arr[2]);getline; print; }'
```

## Explanation:
Explanation
Looking thru another user's shell history just shows epoch times. You can see your own history with pretty timestamps using environment variable HISTTIMEFORMAT and the history command, and you could become another user and run history (which leaves a trail in the shell history).
So, to surreptitiously view another user's shell history and convert epoch to human-readable timestamps, try this one-liner.
Sample Input
#1583857757
history
#1583857774
grep HIST /etc/bashrc
#1583857783
grep HIST /etc/skel/.bash_profile /etc/skel/.bashrc
#1583857945
tail .bash_history

Sample Output
# Tue 10 Mar 2020 04:29:17 PM UTC
history
# Tue 10 Mar 2020 04:29:34 PM UTC
grep HIST /etc/bashrc
# Tue 10 Mar 2020 04:29:43 PM UTC
grep HIST /etc/skel/.bash_profile /etc/skel/.bashrc
# Tue 10 Mar 2020 04:32:25 PM UTC
tail .bash_history

## Limitations:
No limitations specified

