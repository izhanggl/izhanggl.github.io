# Error nginx

`an upstream response is buffered to a temporary file /var/cache/nginx/fastcgi_temp/5/04/0000000045 while reading upstream`

```
#在/etc/nginx/nginx.conf的http作用域里面添加如下配置
fastcgi_buffer_size 8k;
fastcgi_buffers 32 8k;
```

