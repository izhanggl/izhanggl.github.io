# How Linux


## 如何更改时区

`cp /usr/share/zoneinfo/Asia/Shanghai /etc/localtime`

## 如何更改系统语言编码环境

- RHEL7/CenOS7 将`/etc/locale.conf`文件里LANG设置成`LANG="zh_CN.UTF-8"`
- RHEL6/CenOS6 将`/etc/sysconfig/i18n`文件里LANG设置成`LANG="zh_CN.UTF-8"`


## 如何配置服务

显示某个服务的当前状态

- RHEL7/CenOS7 `systemctl status 服务名`
- RHEL6/CenOS6 `service 服务名 status`

启动某个服务

- RHEL7/CenOS7 `systemctl start 服务名`
- RHEL6/CenOS6 `service 服务名 start`

停止某个服务

- RHEL7/CenOS7 `systemctl stop 服务名`
- RHEL6/CenOS6 `service 服务名 stop`

重启某个服务

- RHEL7/CenOS7 `systemctl restart 服务名`
- RHEL6/CenOS6 `service 服务名 restart`

查看服务开机是否启动

- RHEL7/CenOS7 `systemctl list-unit-files`
- RHEL6/CenOS6 `chkconfig --list`

开机启动某个服务

- RHEL7/CenOS7 `systemctl enable 服务名`
- RHEL6/CenOS6 `chkconfig `

开机禁用某个服务

- RHEL7/CenOS7 `systemctl disable 服务名`
- RHEL6/CenOS6 `chkconfig `
