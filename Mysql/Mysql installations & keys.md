## Mysql

Mysqld installation(MYsql installation on redhat
===============================================
> sudo yum install mysql-server -y
> sudo mysql
> If it refused to connect due to socket error them do this:
> sudo service mysqld start( This will display redirecting to /bin/systemctl start mysqld.service)
> sudo systemctl status mysqld
> 
=========================================================
### sudo vi /etc/mysql/mysql.conf.d/mysqld.cnf (for ubuntu, see file down below this page)

### sudo vi /etc/my.cnf (Conf for redhat)

### mysql -h 172.31.25.99 -u webaccess -p tooling tooling-db.sql
==================================================================
### REMI'S REPO, APACHE AND PHP

> sudo yum install httpd -y

> sudo dnf install https://dl.fedoraproject.org/pub/epel/epel-release-latest-9.noarch.rpm

> sudo dnf install dnf-utils http://rpms.remirepo.net/enterprise/remi-release-9.rpm

> sudo dnf module reset php

> sudo dnf module enable php:remi-7.4

> sudo dnf install php php-opcache php-gd php-curl php-mysqlnd

> sudo systemctl start php-fpm

> sudo systemctl enable php-fpm

> setsebool -P httpd_execmem 1

> RESTART PHP:
> sudo systemctl start php-fpm
> sudo systemctl enable php-fpm
> sudo systemctl status php-fpm
======================================================================


### The MySQL database server configuration file.(FOR UBUNTU)
#
### One can use all long options that the program supports.
### Run program with --help to get a list of available options and with
### --print-defaults to see which it would actually understand and use.
#
### For explanations see
### http://dev.mysql.com/doc/mysql/en/server-system-variables.html

### Here is entries for some specific programs
### The following values assume you have at least 32M ram

[mysqld]
#
### * Basic Settings
#
user = mysql
### pid-file = /var/run/mysqld/mysqld.pid
### socket = /var/run/mysqld/mysqld.sock
### port = 3306
### datadir = /var/lib/mysql


### If MySQL is running as a replication slave, this should be
### changed. Ref https://dev.mysql.com/doc/refman/8.0/en/server-system-variables.html#sysvar_tmpdir
### tmpdir = /tmp
#
### Instead of skip-networking the default is now to listen only on
### localhost which is more compatible and is not less secure.
bind-address = 127.0.0.1
mysqlx-bind-address = 127.0.0.1
#
# * Fine Tuning
###
key_buffer_size = 16M
##### max_allowed_packet = 64M
# thread_stack = 256K

### thread_cache_size = -1

### This replaces the startup script and checks MyISAM tables if needed
### the first time they are touched
myisam-recover-options = BACKUP

### max_connections = 151

### table_open_cache = 4000

#
### * Logging and Replication
#
### Both location gets rotated by the cronjob.
#
### Log all queries
### Be aware that this log type is a performance killer.
### general_log_file = /var/log/mysql/query.log
# general_log = 1
#
# Error log - should be very few entries.
#
log_error = /var/log/mysql/error.log
#
# Here you can see queries with especially long duration
# slow_query_log = 1
# slow_query_log_file = /var/log/mysql/mysql-slow.log
# long_query_time = 2
# log-queries-not-using-indexes
#
# The following can be used as easy to replay backup logs or for replication.
# note: if you are setting up a replication slave, see README.Debian about
# other settings you may need to change.
# server-id = 1
# log_bin = /var/log/mysql/mysql-bin.log
# binlog_expire_logs_seconds = 2592000
max_binlog_size = 100M
# binlog_do_db = include_database_name
# binlog_ignore_db = include_database_name

=========================================================================================
=============================================
Windows powershell
============================================================
"C:\Users\Abigail B.Timothy"
============================================================================
* Open security group port 80

* To disables "sudo sentenforce 0"
* sudo vi /etc/sysconfig/selinux
* * Set selinux Disabled
<img width="930" alt="new1" src="https://github.com/Gailpositive/DevOps-Projects-1-10/assets/111061512/b580ec94-ebdf-4ef6-93e1-7d1c0486da0e">

* Quikly go the database, do some config to make sure of the connection
 <img width="491" alt="step 4 15 redhat mysql conf file" src="https://github.com/Gailpositive/DevOps-Projects-1-10/assets/111061512/c85d4fb8-e0f6-4ef3-a439-33d1debb2cf1">

 * Back on the webserver, 
* Update the website configuration to to connect to the database in /var/www/html/functions.php
* sudo vi /var/www/html/functions.php
<img width="673" alt="step 4 13 config function" src="https://github.com/Gailpositive/DevOps-Projects-1-10/assets/111061512/9703196a-8d7f-4271-b832-cb789905d421">

<img width="673" alt="step 4 13 config function" src="https://github.com/Gailpositive/DevOps-Projects-1-10/assets/111061512/9703196a-8d7f-4271-b832-cb789905d421">
* Make sure mysql-y is installed
* cd "tooling"
* mysql-h(private db server ip -u webaccess -p tooling < tooling -db.sql


mysql-h 172.31.25.99-u webaccess -p mypassword < tooling -db.sql

or


mysql -h 172.31.25.99 -u webaccess -p tooling < tooling-db.sql

sudo vi /etc/mysql.conf
