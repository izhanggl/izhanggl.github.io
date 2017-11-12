# 本地YUM源配置

## 服务端配置
将系统盘直接挂载到了/media/目录下面

在/etc/yum.repos.d目录里面创建redhat-media.repo文件并添加如下选项
```
[rhel-media]
name=RHEL6.8
baseurl=file:///media
enabled=1
gpgcheck=1
gpgkey=file:///media/RPM-GPG-KEY-redhat-release
```

- name:自定义名称
- baseurl:本地光盘挂载路径
- enabled:启用yum源，0为不启用，1为启用
- gpgcheck:检查GPG-KEY，0为不检查，1为检查
- gpgkey:GPG-KEY路径


清理缓存

`yum clean all`

安装lrzsz软件包进行测试

`yum install lrzsz`

安装vsftpd实现软件包共享，为局域网其他主机提供YUM服务

`yum install vsftpd`

在/var/ftp/pub/创建RHEL6.8目录进行存放系统光盘里的文件
```
mkdir /var/ftp/pub/RHEL6.8/
cp -rf /media/* /var/ftp/pub/RHEL6.8/
createrepo /var/ftp/pub/RHEL6.8/Server/
```

## 客户端配置
创建文件/etc/yum.repos.d/redhat-ftp.repo并添加如下代码
```
[rhel-media]
name=RHEL6.8
baseurl=ftp://192.168.118.133/pub/RHEL6.8
enabled=1
gpgcheck=1
gpgkey=ftp://192.168.118.133/pub/RHEL6.8/RPM-GPG-KEY-redhat-release
```

## 客户端测试
`yum install lrzsz`
