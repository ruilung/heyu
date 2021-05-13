Build sample laravel(php framework) site
php required package: php7.4,php7.4-fpm,php7.4-mysql
sql server: mysql-5.7
web server: nginx
please config nginx and add new site for laravel default page
virtual hostname: heyu.site

---

ray note>>
base os=centos 7
extra repo=remi / mysql

repo
===

php7.4
---
rpm -ivh  https://rpms.remirepo.net/enterprise/remi-release-7.rpm

mysql5.7
---
rpm -ivh https://repo.mysql.com//mysql-community-release-el7.rpm


Please implement mysqldump backup shell(shell script)
Import sample database(https://github.com/datacharmer/test_db) data to mysql
use sed & awk to dump every database for mysql backup
backup file name: mysql-(%Y%m%d%H)-database_name.tar.gz
Delete Backupfiles older than 10 days using shell script
Build your application to container images and manage your service with docker-compose
Dockerfile
docker-compose.yml
Upload your git repository to public github and must have content below
app                   # application location
.env.example
Dockerfile
docker-compose.yml
README.md             # How to use
