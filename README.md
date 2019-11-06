# cakephp3.7

![56077045-8b3d8d80-5e12-11e9-8f04-6ea41ec2ba54](https://user-images.githubusercontent.com/5633085/56258537-d0abd480-610a-11e9-87ad-26186bc7d7b3.jpg)

tutorials

- CakePHP3.7
- PHP7.2
- Nginx 1.15.5
- Mysql 5.7

## dev

First, please refer to 1 if you are starting for the first time.
Please refer to 2 if you use it after the second time.


- ① If you are starting for the first time

```
fork my repository
$ cd cakephp3.7
$ rm -rf cakephp3/cakephp/*
$ cd docker
$ docker-compose up -d
$ docker exec -it cake3-phpfpm sh
# cd /var/www/html/cakephp3

# php -r "copy('https://getcomposer.org/installer', 'composer-setup.php');"
# php -r "if (hash_file('sha384', 'composer-setup.php') === 'a5c698ffe4b8e849a443b120cd5ba38043260d5c4023dbf93e1558871f1f07f58274fc6f4c93bcfd858c6bd0775cd8d1') { echo 'Installer verified'; } else { echo 'Installer corrupt'; unlink('composer-setup.php'); } echo PHP_EOL;"
# php composer-setup.php
# php -r "unlink('composer-setup.php');"

# php composer.phar create-project --prefer-dist cakephp/app cakephp
# exit

$ cd ../cakephp3/cakephp
$ mv cakephp cakephp33
$ mv cakephp33 ../
$ rm -rf cakephp 
$ mv cakephp33 cakephp
```
- change database

```
$ vim cakephp/config.app.php

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

$ cd ../docker
$ docker-compose down
$ docker-compose up -d

- ② One that starts from the second time
```
fork my repository
$ cd docker
$ docker-compose up -d
```

- accessl url

http://localhost:8080/

![スクリーンショット 2019-04-15 20 49 03](https://user-images.githubusercontent.com/5633085/56130583-49524a00-5fc0-11e9-872f-835d8b1704dc.png)

