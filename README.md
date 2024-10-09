
## 環境

* AmazonLinux2023
* Nginx 1.24.0
* PHP 8.3.10


## ローカル

```bash
$ docker-compose up
```

http://localhost:8080/ にアクセス



## サーバー

### php インストール

```bash
$ dnf search php
$ sudo dnf -y install php php-fpm php-devel php-cli php-common php-mbstring php-mysqlnd php-pdo php-bcmath php-xml php-gd php-gmp
```

### nginx

```bash
$ cd /etc/nginx/conf.d
$ sudo mv php-fpm.conf php-fpm.conf.temp

$ cd /etc/nginx/default.d
$ sudo mv php.conf php.conf.temp
```


### php-fpm

```bash
$ sudo systemctl start php-fpm.service
$ sudo systemctl enable php-fpm.service
```
