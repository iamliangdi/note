# 虚拟机安装centos

- 修改主机名

```shell
> hostnamectl set-hostname base
> systemctl restart systemd-hostnamed.service
> hostname
```

- 修改ip地址

```shell
# 编辑文件
> vi /etc/sysconfig/network-scripts/ifcfg-ens33
# 内容如下
    TYPE=Ethernet
    PROXY_METHOD=none
    BROWSER_ONLY=no
    # BOOTPROTO=dhcp
    BOOTPROTO=static
    DEFROUTE=yes
    IPV4_FAILURE_FATAL=no
    IPV6INIT=yes
    IPV6_AUTOCONF=yes
    IPV6_DEFROUTE=yes
    IPV6_FAILURE_FATAL=no
    IPV6_ADDR_GEN_MODE=stable-privacy
    NAME=ens33
    UUID=9ae1a2ed-a441-407b-b6ae-215930fff479
    DEVICE=ens33
    # ONBOOT=no
    ONBOOT=yes
    # 修改ip
    IPADDR=192.168.31.52
    GATEWAY=192.168.31.2
    NETMASK=255.255.255.0
    DNS1=192.168.31.2
    DNS2=114.114.114.114
# 保存后重启
> reboot
```