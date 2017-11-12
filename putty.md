# PUTTY
## PUTTY不输入密码登录

### Linux服务器设置
* 在远程Linux服务器上生成密钥信息
``` bash
[root@cf ~]# ssh-keygen -t rsa
Generating public/private rsa key pair.
Enter file in which to save the key (/root/.ssh/id_rsa):
Created directory '/root/.ssh'.
Enter passphrase (empty for no passphrase):
Enter same passphrase again:
Your identification has been saved in /root/.ssh/id_rsa.
Your public key has been saved in /root/.ssh/id_rsa.pub.
The key fingerprint is:
d6:b1:41:37:20:e5:0a:e7:4f:2a:f1:63:fc:93:af:1a root@cf
The key's randomart image is:
+--[ RSA 2048]----+
|        ..+.o    |
|         + . .   |
|      . . +      |
|       + o +     |
|      . S +      |
|       = +       |
|      . E ..     |
|       o +o      |
|        ..o+.    |
+-----------------+
[root@cf ~]#
```
* 编辑 /etc/ssh/sshd_config 文件，将如下选项开启
```
RSAAuthentication yes
PubkeyAuthentication yes
```

### 客户端配置
* 在Windows客户端下用PSFTP工具下载远程主机的密钥文件
```
psftp> get -r .ssh
remote:/root/.ssh/id_rsa => local:.ssh\id_rsa
remote:/root/.ssh/id_rsa.pub => local:.ssh\id_rsa.pub
psftp>
```

* 打开PUTTYGEN点击File选择Load private key进行加载下载的id_rsa文件，如在生成密钥时设置了密码就输入设置的密码，没有就点确定。然后点击Save private key

* 打开PAGEANT添加上保存的私钥
