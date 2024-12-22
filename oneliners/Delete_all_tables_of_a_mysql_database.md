# Delete all tables of a mysql database

## Command:
```
$ mysql --defaults-file=my.cnf -e 'show tables' | while read t; do mysql --defaults-file=my.cnt  -e 'drop table '$t; done
```

## Explanation:
Explanation
If you have a root access to the database, a drop database + create database is easiest. This script is useful in situations where you don't have root access to the database.
First prepare a file my.cnf to store database credentials so you don't have to enter on the command line:

[client]
database=dbname
user=dbuser
password=dbpass
host=dbhost

Make sure to protect this file with chmod go-rwx.
The one-liner will execute show tables on the database to list all tables. Then the while loop reads each table name line by line and executes a drop table command.

## Limitations:
Limitations
The above solution is lazy, because not all lines in the output of show tables are table names, so you will see errors when you run it. But hey, shell scripts are meant to be lazy!

