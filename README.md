# Real World Project: Database Shard

This project is done on lubuntu 18.04
	
## Requirements:
---
Linux os: Install clone 
          Install docker-compose
	  Install mariadb-client
---
Python  : Recommend is Pycharm
---
Sql Query: Shard1.sql , Shard2.sql

-
## Linux Steps
---
sudo apt-get update

sudo apt install git

sudo git clone https://github.com/Zohan/maxscale-docker.git

cd maxscale-docker/maxscale/

sudo nano maxscale.cnf (Edited)

sudo nano docker-compose.yml (Edited)

cd maxscale.cnf.d/

sudo nano examples.cnf (Edited)

cd ..

sudo systemctl status docker

sudo apt install docker-compose

sudo apt install maridb-client

sudo docker-compose up -d #(To bring the containers up)

docker-compose exec maxscale maxctrl list servers #(Check server status)

mariadb -umaxuser -pmaxpwd -h 127.0.0.1 -P 4000 #(connect to mariadb)

Welcome to the MariaDB monitor.  Commands end with ; or \g.

Your MariaDB connection id is 12

Server version: 10.5.9-MariaDB-1:10.5.9+maria~focal-log mariadb.org binary distribution

Copyright (c) 2000, 2018, Oracle, MariaDB Corporation Ab and others.

Type 'help;' or '\h' for help. Type '\c' to clear the current input statement.

MariaDB [(none)]> show databases;

-

## Python

Script will query both tables in the databaseIt will output the following information:

1.The last 10 rows of zipcodes_one

2.The first 10 rows of zipcodes_two

3.The largest zipcodenumber in zipcodes_one

4.The smallest zipcode_number in zipcodes_two


---

Once complete, to remove the cluster and maxscale containers:

```
docker-compose down -v

```

-

## Sources:

https://rtc.instructure.com/courses/2054110/files/162256110?module_item_id=52154663
https://github.com/Zohan/maxscale-docker
https://mariadb.com/kb/en/mariadb-maxscale-25-simple-sharding-with-two-servers/
Luma Naser
