# cakephp3.7

![logo-2](https://user-images.githubusercontent.com/5633085/56077045-8b3d8d80-5e12-11e9-8f04-6ea41ec2ba54.jpg)

tutorials

- cakephp3.7
- php7.2

## dev

First, please refer to 1 if you are starting for the first time.
Please refer to 2 if you use it after the second time.


- ① If you are starting for the first time

```
fork my repository
$ rm -rf cakephp3.7/cakephp3/cakephp/*
$ cd docker
$ docker-compose build
$ docker-compose up -d
$ docker exec -it docker_phpfpm_1 sh
# cd /var/www/html/cakephp3

# php -r "copy('https://getcomposer.org/installer', 'composer-setup.php');"
# php -r "if (hash_file('sha384', 'composer-setup.php') === '48e3236262b34d30969dca3c37281b3b4bbe3221bda826ac6a9a62d6444cdb0dcd0615698a5cbe587c3f0fe57a54d8f5') { echo 'Installer verified'; } else { echo 'Installer corrupt'; unlink('composer-setup.php'); } echo PHP_EOL;"
# php composer-setup.php
# php -r "unlink('composer-setup.php');"

# php composer.phar create-project --prefer-dist cakephp/app cakephp
# exit
$ mv cakephp cakephp33
$ mv cakephp33 ../
$ rm -rf cakephp 
$ mv cakephp33 cakephp
```


- ② One that starts from the second time
```
fork my repository
$ cd docker
$ docker-compose build
$ docker-compose up -d
$ docker exec -it docker_phpfpm_1 sh
# cd /var/www/html/cakephp3
# Vendor/bin/cake bake project /var/www/html/cakephp3
# composer create-project --prefer-dist cakephp/app my_app
```
- change database

```
$ cd cakephp3.7/cakephp3/cakephp/config
$ vim app.php

    'Datasources' => [
        'default' => [
            'className' => 'Cake\Database\Connection',
            'driver' => 'Cake\Database\Driver\Mysql',
            'persistent' => false,
            'host' => 'mysql',
            /*
             * CakePHP will use the default DB port based on the driver selected
             * MySQL on MAMP uses port 8889, MAMP users will want to uncomment
             * the following line and set the port accordingly
             */
            //'port' => 'non_standard_port_number',
            'username' => 'root',
            'password' => 'test',
            'database' => 'my_app',

```


- accessl url

http://localhost:8080/

![スクリーンショット 2019-04-15 20 49 03](https://user-images.githubusercontent.com/5633085/56130583-49524a00-5fc0-11e9-872f-835d8b1704dc.png)

