# NGINX

## 部署步骤

部署使用docker容器，docker-compose.yml会将/data/nginx/目录挂进容器里的/etc/nginx目录里;
在系统上安装好docker后，执行如下步骤

``` shell
mkdir /data
cd /data
git clone https://github.com/luo-zn/nginx.git
cd /data/nginx/
docker-compose  up -d
```

## nginx 配置

1. nginx服务的整体配置位于[nginx.conf](/nginx.conf)
2. nginx服务的http公共配置位于[conf.d/features/http.conf](/conf.d/features/http.conf)
3. nginx服务的stream公共配置位于[conf.d/features/stream.conf](/conf.d/features/stream.conf)
4. nginx服务upstreams模块的配置位于[conf.d/upstreams](/conf.d/upstreams)文件夹,根据nginx的特性模块分目录
5. nginx服务server模块的配置位于[conf.d/servers](/conf.d/servers)文件夹,根据nginx的特性模块分目录
6. nginx服务server模块的location配置位于[conf.d/locations](/conf.d/locations)文件夹，文件名根据服务命名
7. [conf.d/locations/static](/conf.d/locations/static)文件夹,存放静态文件的location

***备注：新加的nginx配置应该按照模块和服务放置到对应的目录或者文件里，共用的配置应该放置在公共的地方***
