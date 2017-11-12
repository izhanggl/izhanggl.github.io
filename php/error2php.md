# PHP报错

```
2017/08/02 17:27:22 [error] 382#382: *532 FastCGI sent in stderr: "PHP message: PHP Warning:  session_start(): 
open(/var/lib/php/session/sess_q7prabtgag219f30vm0g43hi74, O_RDWR) failed: Permission denied (13) in /usr/share/nginx/html/wiki/inc/init.php on line 247
PHP message: PHP Warning:  session_write_close(): open(/var/lib/php/session/sess_q7prabtgag219f30vm0g43hi74, O_RDWR) failed: Permission denied (13) in /usr/share/nginx/html/wiki/doku.php on line 121
PHP message: PHP Warning:  session_write_close(): Failed to write session data (files). Please verify that the current setting of session.save_path is correct (/var/lib/php/session) in /usr/share/nginx/html/wiki/doku.php on line 121" while reading response header from upstream, client: 183.240.196.52, server: wiki.cifu.cf, request: "GET /doku.php HTTP/1.1", upstream: "fastcgi://127.0.0.1:9000", host: "wiki.cifu.cf"
```
`chgrp nginx /var/lib/php/session/`

tip:根据自己运行WEB服务的用户和组进行修改，我这里面是nginx用户nginx组
