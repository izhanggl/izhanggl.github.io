# Tiny Tiny RSS

对php的要求
> 版本是5.4或更高
>
> php-mbstring  php-pgsql  php-xml  php-intl要支持

## 设置定时获取订阅信息
```bash
[root@cf ~]# crontab -l
SHELL=/bin/bash
PATH=/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/root/bin

*/10 * * * *  /usr/share/nginx/html/tt-rss/update.php --feeds --quiet
[root@cf ~]#
```

