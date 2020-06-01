## vsftpd

### 1. 安装镜像

```shell
docker pull fauria/vsftpd
```

### 2. 运行容器

```shell
docker run -d --name vsftpd \
-v /docker/app-data/vsftpd:/home/vsftpd \
-p 20:20 -p 21:21 \
-e FTP_USER=xlck-xa-yfzx -e FTP_PASS=Aa1 \
-e PASV_ADDRESS=127.0.0.1 \
--restart=always fauria/vsftpd
```

### 3. 添加新的ftp用户

```shell
docker exec -i -t vsftpd bash
mkdir /home/vsftpd/myuser
echo -e "myuser\nmypass" >> /etc/vsftpd/virtual_users.txt
/usr/bin/db_load -T -t hash -f /etc/vsftpd/virtual_users.txt /etc/vsftpd/virtual_users.db
exit
docker restart vsftpd
```
