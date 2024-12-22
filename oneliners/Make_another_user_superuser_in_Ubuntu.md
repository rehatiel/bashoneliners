# Make another user superuser in Ubuntu

## Command:
```
$ for i in $(grep :boss /etc/group | cut -f1 -d:); do adduser wife $i; done
```

## Explanation:
Explanation
In Ubuntu the first user (created during installation) has special privileges. The privileges come from the fact that the user was automatically added to various system groups. To make another user have the same privileges, all you need to do is add the user to the same groups.

grep :boss /etc/group gets the group records where the user boss is the first member. 
cut -f1 -d: gets the first column, where ":" is the column separator.
for i in ...; do ... ; done for each group it adds the user to the group.

## Limitations:
No limitations specified

