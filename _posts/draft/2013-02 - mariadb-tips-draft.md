Title: Mysql/MariaDB Tips
Date: 2013-02-14 00:00
Tags: development, mysql, database, mariadb

if you are in master or in a production env, and you have to use mysql cli, always enable warning feature `mysql> \W`

use `\G` for `show, select, desc` or anything that need to be printed out on the display.