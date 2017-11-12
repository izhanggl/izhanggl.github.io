# 安装Nginx

## YUM安装Stable version
创建源`/etc/yum.repos.d/nginx.repo`文件并根据自己服务器操作系统版本选择一个添加到文件里面

## CentOS6.x版本的源

```
[nginx]
name=nginx repo
baseurl=http://nginx.org/packages/centos/6/$basearch/
gpgcheck=0
enabled=1
```

## CentOS7.x版本的源
```
[nginx]
name=nginx repo
baseurl=http://nginx.org/packages/centos/7/$basearch/
gpgcheck=0
enabled=1
```

## RHEL6.x版本的源
```
[nginx]
name=nginx repo
baseurl=http://nginx.org/packages/rhel/6/$basearch/
gpgcheck=0
enabled=1
```

## RHEL7.x版本的源
```
[nginx]
name=nginx repo
baseurl=http://nginx.org/packages/rhel/7/$basearch/
gpgcheck=0
enabled=1
```

## YUM安装nginx
```
yum install nginx
```
