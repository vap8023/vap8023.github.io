## Docker-compose
作用：
- 互访问题
- 顺序依赖

## 安装
国外镜像地址：
```shell
sudo curl -L "https://github.com/docker/compose/releases/download/1.29.2/docker-compose-$(uname -s)-$(uname -m)" -o /usr/local/bin/docker-compose
```

国内镜像地址：
```shell
sudo curl -L https://get.daocloud.io/docker/compose/releases/download/1.24.0/docker-compose-`uname -s`-`uname -m` > /usr/local/bin/docker-compose
```

赋予执行权限：
```shell
sudo chmod +x /usr/local/bin/docker-compose
```

检查安装：
```shell
docker-compose -version
```
如果能够出现版本信息，说明安装没有问题；