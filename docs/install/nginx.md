## nginx

### 安装镜像

```shell
docker pull nginx
```

### 创建容器

```shell
docker run --name nginx -d -p 80:80 nginx
```

### 创建本地nginx配置文件夹

```shell
sudo mkdir /docker/app-conf/nginx/
```

### 复制容器中的nginx.conf文件到本地配置文件夹中

```shell
sudo docker cp nginx:/etc/nginx/nginx.conf /docker/app-conf/nginx/
```

### 停止nginx容器

```shell
docker stop nginx
```

### 删除容器

```shell
docker rm nginx
```

### 重新创建容器

```shell
docker run --name nginx -d \
-v /docker/app-data/nginx/html:/usr/share/nginx/html \
-v /docker/app-conf/nginx/nginx.conf:/etc/nginx/nginx.conf \
-v /docker/app-log/nginx:/var/log/nginx \
-p 80:80 nginx
```

### 编辑nginx.conf文件

```shell
sudo vim /docker/app-conf/nginx/nginx.conf
```

在http节点中添加以下节点：

```json
server {
    listen    80;
    server_name    gitlab.harris.com;
    location / {
        proxy_pass http://172.16.2.35:10080;
    }    
}

server {
    listen    80;
    server_name    zbox.harris.com;
    location / {
        proxy_pass http://172.16.2.35:8930;
    }    
}

```

### 重启容器

```shell
docker restart nginx
```


