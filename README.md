# Alpine NGINX LUA Docker image

Simple Docker Alpine Nginx image with LUA support

## Installation

Either download it from [hub.docker.com](https://hub.docker.com/r/xnevo/alpine-nginx-lua) or build it yourself Download:

``` 
docker pull xnevo/docker-alpine-nginx-lua:1.13.7
OR
docker pull registry.lumen.sh/lumen/docker-alpine-nginx-lua:1.13.7
```

Build from source: 

``` 
docker build -t nginx-lua:1.13.7 .
```

## Configuration

Mount your configuration in the following location in order to apply your nginx configuration 

``` 
/etc/nginx 
``` 

Example: 

``` 
docker run -it --name nginx-server -d -v /my/configuration:/etc/nginx -p 80:80 -p 443:443 registry.lumen.sh/lumen/docker-alpine-nginx-lua:1.13.7
```

If you don't have a configuration yet, you can copy nginx's default configuration by running the following commands

```
docker run -it --rm --name nginx-temp -d -v /your/config/path:/tmp/nginx registry.lumen.sh/lumen/docker-alpine-nginx-lua:1.13.7 && sleep 2 \
&& docker exec -it nginx-temp /bin/cp -R /etc/nginx /tmp/ \
&& docker stop nginx-temp
```
