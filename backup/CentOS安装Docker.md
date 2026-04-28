# 安装依赖
```shell
yum install - y yum-utils device-mapper-persistent-data lvm2
```

# 配置yum源
```shell
yum-config-manager --add-repo https://mirrors.ustc.edu.cn/docker-ce/linux/centos/docker-ce.repo
```

# 更新缓存
```shell
yum makecache fast

yum install docker-ce
```

# 启动docker
```shell
systemctl enable docker
systemctl start docker
```

# 镜像加速
```shell
vi /etc/docker/daemon.json
# docker-cn
{
  "registry-mirrors": ["https://registry.docker-cn.com"]
}
# 腾讯
{
  "registry-mirrors": ["https://mirror.ccs.tencentyun.com"]
}
```