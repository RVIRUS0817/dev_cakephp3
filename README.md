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
$ vim cake3.7/cakephp3/cakephp/composer.json

"require": {
    "cakephp/cakephp": "3.7.*"
}

$ cd docker
$ docker-compose build
$ docker-compose up -d
$ docker exec -it docker_phpfpm_1 sh
$ cd /var/www/html/cakephp3
$ php composer.phar create-project --prefer-dist cakephp/app my_app
```


- ② One that starts from the second time
```
fork my repository
$ cd docker
$ docker-compose build
$ docker-compose up -d
$ docker exec -it docker_phpfpm_1 sh
$ cd /var/www/html/cakephp3
$ Vendor/bin/cake bake project /var/www/html/cakephp3
$ composer create-project --prefer-dist cakephp/app my_app
```


- accessl url

http://localhost:8080/

