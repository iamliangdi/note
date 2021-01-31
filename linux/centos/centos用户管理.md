# centos用户管理

## 1. 新增用户

```shell
# 添加用户
> adduser test
# 创建密码
> passwd test
```

## 2. 赋予用户管理员权限

```shell
# 编辑文件
> vi /etc/sudoers
# 仿照root把test用户写入root下行即可
```

## 3. 删除用户

```shell
# 仅删除用户
> userdel test
# 删除用户同时删除用户文件夹
> userdel -r test
```