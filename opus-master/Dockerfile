FROM php:7-fpm

RUN apt-get update > /dev/null \
    && apt-get install -yyq \
    libmcrypt-dev \
    libpng12-dev \
    libfreetype6-dev \
    libjpeg62-turbo-dev \
    git \
    curl \
    unzip \
    zip \
    > /dev/null \
    && docker-php-ext-install \
    pdo_mysql \
    iconv \
    pdo \
    zip \
    mcrypt \
    > /dev/null \
    && docker-php-ext-enable \
    pdo_mysql \
    iconv \
    pdo \
    zip \
    mcrypt \
    > /dev/null \
    && apt-get clean \
    && rm -rf /var/lib/apt/lists/* /tmp/* /var/tmp/*

RUN php -r "copy('https://getcomposer.org/installer', 'composer-setup.php');"
RUN php -r "if (hash_file('SHA384', 'composer-setup.php') === '669656bab3166a7aff8a7506b8cb2d1c292f042046c5a994c43155c0be6190fa0355160742ab2e1c88d40d5be660b410') { echo 'Installer verified'; } else { echo 'Installer corrupt'; unlink('composer-setup.php'); } echo PHP_EOL;"
RUN php composer-setup.php
RUN php -r "unlink('composer-setup.php');"

RUN mv composer.phar /usr/local/bin/composer

WORKDIR /usr/local/etc/php/conf.d
ADD conf/php.ini custom.ini

WORKDIR /var/www/html/
RUN git clone -q https://github.com/zeeshanu/opus.git opus
WORKDIR opus
ADD conf/.env .env
# TODO: Make posible change branches before install
#active_version=$(git status | head -1)
#if [ "$active_version" != "HEAD detached at $version" ]; then
#    echo "Switching to version $version ..."
#    git fetch -q
#    git checkout -q $version
#fi

RUN composer install --no-plugins --no-scripts
# RUN php artisan migrate
# RUN php artisan key:generate
# RUN php artisan db:seed
