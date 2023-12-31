# ecos-docker-compose

Clone repo in need folder (this "/app"):
```
mkdir /app/ecos
git clone https://github.com/DeAlexPesh/ecos-docker-compose.git /app
```

Edit files with params: /app/compose/ecos/.env
```
mv /app/compose/ecos/ecos.env /app/compose/ecos/.env
nano /app/compose/ecos/.env
```
```
...
PROXY_HOST=ecos-community-demo   # domain name
...
ECOS_SRC_PATH=/app/ecos   # path to data volumes
```
Other in /app/compose/ecos/env/*

## Test configuration
docker-compose -f /app/compose/ecos/ecos.yml config

## Download images
docker-compose -f /app/compose/ecos/ecos.yml pull

## Run apps
docker-compose -f /app/compose/ecos/ecos.yml up -d
```
* 4Gb RAM is low for this monster...
```

## Testing domain host bind (on machine with client browser)
```
sed -i '1 i\127.0.0.1 ecos-community-demo' /etc/hosts
```
```
http://ecos-community-demo
admin | admin
```

## Kill the Developer...
docker-compose -f /app/compose/ecos/ecos.yml down
