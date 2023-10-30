# Mysql with phpmyadmin docker container

## Clone:
```
git clone git@github.com:sagormax/docker-mysql-phpmyadmin.git
```

## Configuration:
```
Mysql: 8.2.0 (MySQL Community Server - GPL)
innodb_version: 8.2.0
```

## Setup and run from root directory:
```
docker-compose up -d
```

## phpmyadmin:
http://localhost:8089
```
USER: docker_mysql
PASSWORD: docker_mysql
```

## Mysql server EXPOSE PORT:
```
HOST: localhost
PORT: 3307
MYSQL_ROOT_PASSWORD=docker_mysql_root
MYSQL_DATABASE=docker_mysql
MYSQL_USER=docker_mysql
MYSQL_PASSWORD=docker_mysql
```
