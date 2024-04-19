# Deployment with docker-compose - main-api example


## Requirements
- Docker
- Docker compose

### How to install - EC2 instance example ubuntu 22

```
# Docker install

apt-get update
apt-get install docker.io --yes

# Docker Compose install

curl -L https://github.com/docker/compose/releases/download/1.28.5/docker-compose-`uname -s`-`uname -m` -o /usr/local/bin/docker-compose
chmod +x /usr/local/bin/docker-compose
```

## Instalations

### Clone example repository

```
cd /home/ubuntu
git clone https://github.com/paulspartan14/docker-production-environment-workshop.git
cd docker-production-environment-workshop/
```

### first up nginx-proxy containers (make sure open ports 443 and 80 on Segurity Group)

```
cd 01-nginx-proxy
docker-compose up -d
docker-compose logs -f
```

### up main api and validate if it's works (needs attach specific DNS record and update ENV)

```
cd ..
cd 02-main-api
docker-compose up -d
docker-compose logs -f
```

### (optional) up metrics collector and monitoring dashboard (needs attach specific DNS record and update ENV)

```
cd ..
cd 03-metrics-collector
docker-compose up -d
docker-compose logs -f

cd .
cd 04-metrics-collector
docker-compose up -d
docker-compose logs -f

```
