# Iac-PrestaShop

This is IaC for simple prestashop project and besed on official docker images
## Version:
- Prestashop: lastest
- Redis: latest
- MariaDB: latest
- treafik: lastest
## Architecture:
There is 3 containers (treafik,prestashop,db)

Web (PHP 9000) <-> Nginx(8080)

Redis (Redis 6379) <-> Web

mariadb(3306) <-> Web


## Docker & Docker-compose installation
### Linux

See official documentation : [docker ubuntu](https://docs.docker.com/engine/install/ubuntu/)

Docker compose is also needed:

```bash
sudo curl -L "https://github.com/docker/compose/releases/download/1.28.2/docker-compose-$(uname -s)-$(uname -m)" -o /usr/local/bin/docker-compose
```

## Usage
1- copy the IaC Files to the root of your project

2- Run  
```bash
docker-compose up 
```
I you made somme changes in the dockerFile or the config files you Have to rebuild the images:
```bash
docker-compose up --build
```

2- Edit and reconfigure the env-docker.php if needed and copy it to magento etc.
```bash
cp env-docker.php ./app/etc/env.php
```

2- Run  
```bash
docker-compose up 
```
I you made somme changes in the dockerFile or the config files you Have to rebuild the images:
```bash
docker-compose up --build
```

4- Stop
```bash
docker-compose stop 
```
You can stop and remove the containers without losing the data of the volumes (MariaDB + Redis)

```bash
docker-compose down
```
3- To interact with the web container using bash cmd
```bash
docker-compose exec web /bin/bash
```


