##常用模块
`ansible-doc 模块名称`查看模块详细用法
##comand
```
[root@SH ~]# ansible test -m command -a "ls /tmp" -k
SSH password: 
192.168.245.136 | SUCCESS | rc=0 >>
ansible_pE1jve
yum.log
yum_save_tx-2017-10-19-23-16RKRTKa.yumtx

[root@SH ~]# 
```
##shell
```
[root@SH ~]# ansible test -m shell -a "cat /etc/selinux/config | grep -v ^# | grep -v ^$" -k
SSH password: 
192.168.245.136 | SUCCESS | rc=0 >>
SELINUX=enforcing
SELINUXTYPE=targeted 

[root@SH ~]# 
```
##copy
将本地/root/ha.txt上传到目标主机的/root目录
```
[root@SH ~]# ansible test -m copy -a 'src=/root/ha.txt dest=/root' -k
SSH password: 
192.168.245.136 | SUCCESS => {
    "changed": true, 
    "checksum": "8afe63e7fca071b3660862cf82ea8e6ce81da056", 
    "dest": "/root/ha.txt", 
    "gid": 0, 
    "group": "root", 
    "md5sum": "d5ed80ccd20fb3dc6f5aeb1d94631be7", 
    "mode": "0644", 
    "owner": "root", 
    "secontext": "system_u:object_r:admin_home_t:s0", 
    "size": 10, 
    "src": "/root/.ansible/tmp/ansible-tmp-1508437944.16-260602010531903/source", 
    "state": "file", 
    "uid": 0
}
[root@SH ~]# 
```
##service
