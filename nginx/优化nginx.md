# 优化nginx

## gzip

```
    gzip on;	# 开启gzip
    gzip_min_length 1k;     # 最小阀值
    gzip_comp_level 2;      # 压缩比 1-9 级别越高占用cpu资源越多
    gzip_types text/plain application/javascript application/x-javascript text/css application/xml text/javascript application/x-httpd-php image/jpeg image/gif image/png font/ttf font/otf image/svg+xml;	## 压缩文件类型
    gzip_vary on;                   # 启用gzip压缩标识
    gzip_disable "MSIE [1-6]\.";    # 禁用ie6以下的gzip压缩功能

    #gzip_buffers 4 16k;      # 设置系统获取几个单位的缓存用于存储gzip的压缩结果数据流。4 16k代表以16k为单位，安装原始数据大小以16k为单位的4倍申请内存。
    #gzip_http_version 1.0;  # http协议版本 现在一般都是1.1了
```
