# ubuntu18.04安装docker

### 卸载老版本docker

```shell
sudo apt-get remove docker docker-engine docker.io containerd runc
```

### 安装新版本

```shell
sudo apt-get update
```

```shell
sudo apt-get install \
    apt-transport-https \
    ca-certificates \
    curl \
    gnupg-agent \
    software-properties-common
```

```shell
curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo apt-key add -
```

```shell
sudo add-apt-repository \
   "deb [arch=amd64] https://download.docker.com/linux/ubuntu \
   $(lsb_release -cs) \
   stable"
```

```shell
sudo apt-get update
```

```shell
sudo apt-get install docker-ce docker-ce-cli containerd.io
```

```shell
sudo usermod -aG docker your-user
```