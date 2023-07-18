# ecos-docker-compose

Clone repo in need folder (this "/app"):
```
git clone https://github.com/DeAlexPesh/ecos-docker-compose.git /app
```
```
sudo mkdir -p /app/ecos
```

Edit files with params: /app/compose/ecos/.env
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

## Testing domain host bind (on machine with client browser)
```
sed -i '1 i\127.0.0.1 ecos-community-demo' /etc/hosts
```
```
http://ecos-community-demo
admin | admin
```

```
* 4Gb RAM is low for this monster...
```

## Kill the Developer...
docker-compose -f /app/compose/ecos/ecos.yml down
