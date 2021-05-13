Build sample laravel(php framework) site
php required package: php7.4,php7.4-fpm,php7.4-mysql
sql server: mysql-5.7
web server: nginx
please config nginx and add new site for laravel default page
virtual hostname: heyu.site

```


base os=centos 7
extra repo=remi / mysql



php7.4 repo
---
rpm -ivh  https://rpms.remirepo.net/enterprise/remi-release-7.rpm

mysql5.7 repo
---
rpm -ivh https://repo.mysql.com/mysql57-community-release-el7.rpm

selinux
---
setenforce 0
#for lab

software install
---
yum install nginx git 
yum install mysql-server
yum install php74 php74-php-fpm php74-php-mysql composer

service
---
systemctl enable --now nginx mysqld php74-php-fpm

test db installaion
---
git clone https://github.com/datacharmer/test_db .
mysql < employees.sql
#lab store user/pd in my.cnf


nginx config
---
root@localhost conf.d]# cat heyu.conf  #disable default webserver in nginx.conf
server {
listen   80 default_server;

root /var/www/php/testproj/;
server_name _; #heyu.site >> wildcard for lab 

index index.php;

location ~ \.php$ {
  root /var/www/php/testproj;
  fastcgi_pass 127.0.0.1:9000;
  fastcgi_index index.php;
  fastcgi_param SCRIPT_FILENAME $document_root$fastcgi_script_name;
  include fastcgi_params;
  }
}


lavaral project
----
mkdir -p /var/www/php
cd /var/www/php
composer create-project --prefer-dist laravel/laravel testproj

[root@localhost testproj]# cat index.php 
<?php
phpinfo();
?>
#test for php-fpm working or not





```




Please implement mysqldump backup shell(shell script)
Import sample database(https://github.com/datacharmer/test_db) data to mysql
use sed & awk to dump every database for mysql backup
backup file name: mysql-(%Y%m%d%H)-database_name.tar.gz
Delete Backupfiles older than 10 days using shell script
```
db list
===
# mysql -e 'show databases;'|awk -F " " '{if (NR!=1) print $1}'
information_schema
employees
mysql
performance_schema
sys

```





Build your application to container images and manage your service with docker-compose
Dockerfile
docker-compose.yml
Upload your git repository to public github and must have content below
app                   # application location
.env.example
Dockerfile
docker-compose.yml
README.md             # How to use
