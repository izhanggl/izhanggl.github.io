# raspberry pi
## 源配置
需要更改2个文件`/etc/apt/sources.list`和`/etc/apt/sources.list.d/raspi.list`

将/etc/apt/sources.list原来的源注释掉并添加如下信息
```
#use ustc mirror
deb http://mirrors.ustc.edu.cn/raspbian/raspbian/ jessie main contrib non-free rpi
```
将/etc/apt/sources.list.d/raspi.list原来的源注释掉并添加如下信息
```
#use ustc mirror
deb http://mirrors.ustc.edu.cn/archive.raspberrypi.org/ jessie main ui
```
