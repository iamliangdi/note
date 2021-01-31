# docker在centos环境下的安装

- 卸载旧版本

```shell
> sudo yum remove docker \
                  docker-client \
                  docker-client-latest \
                  docker-common \
                  docker-latest \
                  docker-latest-logrotate \
                  docker-logrotate \
                  docker-engine
```

- 安装所需的软件包

```shell
> sudo yum install -y yum-utils \
  device-mapper-persistent-data \
  lvm2
```

- 设置稳定的存储库

```shell
> sudo yum-config-manager --add-repo http://mirrors.aliyun.com/docker-ce/linux/centos/docker-ce.repo
```

- 安装

```shell
> sudo yum install docker-ce docker-ce-cli containerd.io
```

- 验证

```shell
> docker version
```

- 配置镜像加速器(阿里云获取)

```shell
# 创建目录
> mkdir /etc/docker
# 创建文件并写入内容
> vi /etc/docker/daemon.json
{
  "registry-mirrors": ["https://xxxxxxxx.mirror.aliyuncs.com"]
}
```

- 重启docker

```shell
> systemctl daemon-reload
> systemctl restart docker
```

- 验证

```shell
> docker info
```

- 将用户添加到docker组

```shell
# 保留原有的组情况下追加组
> sudo usermod -aG docker test
# 或
> sudo gpasswd -a test docker
```