FROM php:7.2.10-fpm-stretch
RUN apt-get update && \
    apt-get install -y curl git zip unzip libicu-dev && \ 
    php -r "copy('https://getcomposer.org/installer', 'composer-setup.php');" && \
    php -r "if (hash_file('sha384', 'composer-setup.php') === 'a5c698ffe4b8e849a443b120cd5ba38043260d5c4023dbf93e1558871f1f07f58274fc6f4c93bcfd858c6bd0775cd8d1') { echo 'Installer verified'; } else { echo 'Installer corrupt'; unlink('composer-setup.php'); } echo PHP_EOL;" && \
    php composer-setup.php && \
    php -r "unlink('composer-setup.php');" && \
    mv composer.phar /usr/local/bin/composer && \
    docker-php-ext-install intl pdo_mysql mbstring && \
    composer config -g repos.packagist composer https://packagist.jp && \
    composer global require hirak/prestissimo
