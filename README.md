# Mysql with phpmyadmin, PostgreSQL, MongoDB with Mongo-Express docker container

## Clone:
```
git@github.com:sagormax/docker-mysql-phpmyadmin.git
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

## Additional PostgreSQL:
### Uncomment following lines for docker-compose.yml file
```
# postgresql:
  #   container_name: docker-postgresql
  #   platform: linux/arm64/v8
  #   image: 'bitnami/postgresql:latest'
  #   restart: unless-stopped
  #   ports:
  #     - 54321:5432
  #   volumes:
  #     - postgresql_db_data:/bitnami/postgresql
  #   environment:
  #     - POSTGRESQL_USERNAME=${POSTGRESQL_USERNAME}
  #     - POSTGRESQL_PASSWORD=${POSTGRESQL_PASSWORD}
  #     - POSTGRESQL_DATABASE=${POSTGRESQL_DATABASE}
  #     - POSTGRESQL_POSTGRES_PASSWORD=${POSTGRESQL_POSTGRES_PASSWORD}
```
## PostgreSQL EXPOSE PORT:
```
PORT: 54321
DATABASE: docker_postgresql

# you can update those from .env file
POSTGRESQL_DATABASE=docker_postgresql
POSTGRESQL_USERNAME=docker_postgresql
POSTGRESQL_PASSWORD=docker_postgresql
POSTGRESQL_POSTGRES_PASSWORD=docker_postgresql_root
```


## Additional MongoDB:
### Uncomment following lines for docker-compose.yml file
```
# mongodb:
  #   container_name: docker-mongodb
  #   platform: linux/arm64/v8
  #   image: mongo:latest
  #   restart: unless-stopped
  #   ports:
  #     - 27017:27017
  #   volumes:
  #     - mongodb_db_data:/data/db
  #   environment:
  #     MONGO_INITDB_ROOT_USERNAME: ${MONGO_INITDB_ROOT_USERNAME}
  #     MONGO_INITDB_ROOT_PASSWORD: ${MONGO_INITDB_ROOT_PASSWORD}
  #   networks:
  #     - docker-mysql-network

  # mongodb-express:
  #   container_name: docker-mongodb-express
  #   depends_on:
  #     - mongodb
  #   image: mongo-express:latest
  #   restart: unless-stopped
  #   ports:
  #     - 8087:8081
  #   environment:
  #     ME_CONFIG_MONGODB_ADMINUSERNAME: ${MONGO_INITDB_ROOT_USERNAME}
  #     ME_CONFIG_MONGODB_ADMINPASSWORD: ${MONGO_INITDB_ROOT_PASSWORD}
  #     ME_CONFIG_MONGODB_URL: mongodb://${MONGO_INITDB_ROOT_USERNAME}:${MONGO_INITDB_ROOT_PASSWORD}@mongodb:27017/
  #   networks:
  #     - docker-mysql-network
```

## Mongo-Express:
http://localhost:8087
```
USER: admin
PASS: pass
```

## MongoDB EXPOSE PORT and basic auth:
```
PORT: 27017

# you can update those from .env file
MONGO_INITDB_ROOT_USERNAME=docker_mongo
MONGO_INITDB_ROOT_PASSWORD=docker_mongo
```
