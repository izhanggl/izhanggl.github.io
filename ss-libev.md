# ss-libev

## 服务器安装

安装依赖的包
```
yum install epel-release -y
yum install gcc gettext autoconf libtool automake make pcre-devel asciidoc xmlto udns-devel libev-devel libsodium-devel mbedtls-devel -y
```
去https://github.com/shadowsocks/shadowsocks-libev下载ss-libev并编译安装
```
tar xzf shadowsocks-libev-3.0.8.tar.gz
cd shadowsocks-libev-3.0.8
./configure
make
make install
```

设置开机启动
我的VPS是CentOS7需要做如下配置
编写名为service2on.sh的脚本，内容如下并设置执行权限
```
#!/bin/bash

ss-server  -p 开放的端口号 -k 密码 -m aes-256-cfb
```

在/etc/rc.local的最后添加刚编写的脚本
`/root/service2on.sh`

最后给rc.local可执行权限
`chmod +x /etc/rc.d/rc.local`

你可以把ss-libev的配置信息在放在文件里面如下
```
{
    "server":"168.235.92.129",
    "server_port":8388,
    "local_port":1080,
    "password":"123456",
    "timeout":60,
    "method":"aes-256-cfb"
}
```

- Server 写入你VPS的IP地址
- server_port 设定一个开放端口
- local_port 一个本地端口
- password 密码喽
- timeout 超时时间设定
- method 加密类型

## 客户端

- Windows https://github.com/shadowsocks/shadowsocks-windows
- Linux https://github.com/shadowsocks/shadowsocks-qt5/wiki/Installation
  - GUI Client
    Fedora
    ```
    sudo dnf copr enable librehat/shadowsocks
    sudo dnf update
    sudo dnf install shadowsocks-qt5
   ```
  - Command-line Client
    - `pip install shadowsocks`
    - `apt-get install shadowsocks-libev`
    - `cpan Net::Shadowsocks`
    
- 安卓手机 http://pan.baidu.com/s/1dFnJoZn
