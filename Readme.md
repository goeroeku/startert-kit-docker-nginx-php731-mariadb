# Starter Kit Docker PHP

## General user

1. clone this repo
   the output is laravel-app, change laravel-app with dot (.) if you don't want to create directory laravel-app. Ex: run git clone in project directory

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
   Use server: db if using docker container, ex: scripting on connection.php
   Or use server: 127.0.0.1 if you want to access container laravel_db from host (not from container), ex: php artisan migrate

```text
server    : db
port      : 3306
username  : root  or  homestead
password  : secret
database  : homestead
driver    : mysql
```

5. access app

```text
localhost:9090
```

## for laravel user

1. modify nginx config, see: point 2 before
2. put laravel code to htdocs
3. install composer, php cli, php pdo, php mysql, php pdo_mysql, php pdo_pgsql (optional)
4. install library php for laravel using composer

```text
# composer install
```

5. use .env in example directory (optional)
6. generate key for laravel

```text
# php artisan key:generate
```

7. run migration

```text
# php artisan migrate
```

## Error

### PDOException::("could not find driver")

- Pastikan php, php pdo, php mysql, php pdo mysql sudah terinstall

```text
# php -m | grep mysql
```

- Jika belum muncul pdo mysql, install dahulu kemudian aktifkan modul tersebut pada file php.ini

contoh lokasi file php.ini pada /etc/php/php.ini

```text
# vim /etc/php/php.ini
```

cari extension pdo_mysql, harusnya:

```text
;extension=pdo_mysql
```

hilangkan titik koma (;), sehingga menjadi

```text
extension=pdo_mysql
```

keluar dari vim dan jangan lupa simpan perubahan
