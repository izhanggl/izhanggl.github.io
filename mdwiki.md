MDwiki
======

安装
====
[下载MDwiki](https://github.com/Dynalon/mdwiki/releases)，解压后目录结构如下，平常用到的只用一个mdwiki.html
```bash
[root@cf ~]# unzip mdwiki-0.6.2.zip 
Archive:  mdwiki-0.6.2.zip
   creating: mdwiki-0.6.2/
  inflating: mdwiki-0.6.2/LICENSE.txt  
  inflating: mdwiki-0.6.2/mdwiki-debug.html  
  inflating: mdwiki-0.6.2/README.md  
  inflating: mdwiki-0.6.2/mdwiki.html  
  inflating: mdwiki-0.6.2/GPLv3.txt  
  inflating: mdwiki-0.6.2/mdwiki-slim.html 
[root@cf ~]#
```
在你的WEB开放目录我这是`/usr/share/nginx/html/`下新建一个mdwiki目录`，用于存放mdwiki.html文件以及以后你写的Markdown文件

MDwiki的工作方式是`http://www.example.com/mdwiki.html#!myfile.md`用mdwiki.html来解释你写的Markdown文件
你如果把mdwiki.html重命令为index.html就可以以`http://www.example.com/#!myfile.md`来访问你的myfile.md
你如果在mdwiki目录下新建index.md通过`http://www.example.com/`就会默认打开index.md，推荐新建index.md来当wiki主页

配置
===

图片布局

* 图片链接在上，紧挨着另起一行是文字--》显示效果为图片在左边，文字在右边
```markdown
![](http://placekitten.com/g/800/800)
The above image floats left to this text.
```
* 图片链接在下，文字在图片链接的上面--》显示效果为图片在右边，文字在左边
```markdown
The images below float right to this text.
Lorem ipsum dolor sit amet, consectetuer adipiscing elit, sed diam nonummy nibh euismod tincidunt ut laoreet dolore magna aliquam erat volutpat.
![](http://placekitten.com/g/600/600)
```
* 图片链接跟文字中间如果有空行，就没有格式效果


