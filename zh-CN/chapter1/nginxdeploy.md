---
name: Nginx部署
---

## Nginx部署

### 创建相关目录
```sh
mkdir -p /data/{soft,src}
cd /data/src
```

### 上传及解压
上传 nginx_1.10.3_deploy.tar.gz
```sh
tar xf nginx_1.10.3_deploy.tar.gz -C /data/soft
```

### 创建用户
```sh
useradd -M -s /sbin/nologin -u 10001 nginx
```

### 部署
```sh
cd /data/soft/nginx
\cp -a add/nginx.conf conf/
\cp -a add/default.conf conf/vhosts/
\cp -a add/nginx_init.d /etc/rc.d/init.d/nginx
\cp -a add/nginx_logrotate.d /etc/logrotate.d/nginx
#chmod +x /etc/rc.d/init.d/nginx
chkconfig --add nginx
chkconfig nginx on
```

```sh
mkdir -p /data/www/default
#chown -R nginx.nginx /data/www
```

### 启动及测试
```sh
service nginx start
netstat -tnlup
curl 127.0.0.1/nginx_status
```



