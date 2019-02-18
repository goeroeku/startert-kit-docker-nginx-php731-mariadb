# Starter Kit Docker PHP

1. clone this repo
   the output is laravel-app

```text
# git clone git@github.com:goeroeku/startert-kit-docker-nginx-php731-mariadb.git laravel-app
```

2. put your php project in htdocs
   if using laravel, edit nginx.conf, change root location to /var/www/html/public

```text
  root /var/www/html/public;
```

then clone master of laravel to directory htdocs

```text
# cd htdocs
# git clone https://github.com/laravel/laravel .
```

or using laravel installer (googling pls ;p)

3. docker-compose up in root directory

4. database server

```text
server    : db
port      : 3306
username  : root
password  : secret
driver    : mysql
```

5. access app

```text
localhost:9090
```
