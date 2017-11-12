#Ansible报错汇总
```
[root@SH ansible]# ansible test -m ping
192.168.245.136 | UNREACHABLE! => {
    "changed": false,
    "msg": "Failed to connect to the host via ssh: Permission denied (publickey,gssapi-keyex,gssapi-with-mic,password).\r\n",
    "unreachable": true
}
```
tip:出现上面这种情况加入-k选项`ansible test -m ping  -k`
```
root@SH ~]# ansible test -m copy -a 'src=/root/ha dest=/root' -k
SSH password:
192.168.245.136 | FAILED! => {
    "changed": false,
    "checksum": "8afe63e7fca071b3660862cf82ea8e6ce81da056",
    "failed": true,
    "msg": "Aborting, target uses selinux but python bindings (libselinux-python) aren't installed!"
}
```
tip:因为在被管理的机器上没有安装libselinux-python，系统安装盘里面有这个包找到直接使用`rpm -ivh rpm -ivh  libselinux-python-2.0.94-7.el6.x86_64.rpm `进行安装即可。还有一种方法就是在>被管理的机器上关闭selinux。注意:是在被管理的机器上安装包或者关闭selinux，不是在安装了ansiable的机器上安装
