# 禅道

## 安装镜像

```shell
docker pull idoop/zentao
```

## 创建容器

```shell
docker run -d -p 8930:80 -p 3306:3306 \
-e ADMINER_USER="admin" -e ADMINER_PASSWD="123456" \
-e BIND_ADDRESS="false" \
-v /docker/app-data/zbox/:/opt/zbox/ \
--name zbox \
idoop/zentao:latest
```

