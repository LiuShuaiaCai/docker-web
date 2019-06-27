FROM php:fpm
# MAINTAINER liushuaicai<liushuaicai@100tal.com>

ENV TZ "Asia/Shanghai"

RUN docker-php-ext-install pdo_mysql
RUN docker-php-ext-install mysqli && docker-php-ext-enable mysqli
RUN docker-php-ext-install pdo_mysql
RUN docker-php-ext-install sockets
RUN docker-php-ext-install bcmath

RUN apt-get update && apt-get install gzip 
RUN mkdir -p /usr/src/php/ext/redis \
    && curl -L http://pecl.php.net/get/redis-4.1.1.tgz | tar xvz -C /usr/src/php/ext/redis --strip 1 \
    && echo 'redis' >> /usr/src/php-available-exts \
    && docker-php-ext-install redis

RUN apt-get install wget
RUN mkdir -p /usr/local/autoconf \
    && cd /usr/local/autoconf \
    && wget ftp://ftp.gnu.org/gnu/autoconf/autoconf-2.69.tar.gz \
    && tar zxvf autoconf-2.69.tar.gz \
    && cd autoconf-2.69 \
    && ./configure \
    && make \
    && make install


RUN mkdir -p /usr/src/php/ext/rabbitmq \
    && cd /usr/src/php/ext/rabbitmq \
    && wget https://github.com/alanxz/rabbitmq-c/releases/download/v0.5.2/rabbitmq-c-0.5.2.tar.gz  \
    && tar zxvf rabbitmq-c-0.5.2.tar.gz \
    && cd rabbitmq-c-0.5.2 \
    && /usr/local/bin/autoconf -i \
    && ./configure \
    && make && make install

RUN mkdir -p /usr/src/php/ext/amqp \
    && curl -L http://pecl.php.net/get/amqp-1.7.0.tgz | tar xvz -C /usr/src/php/ext/amqp --strip 1 \
    && echo 'amqp' >> /usr/src/php-available-exts \
    && docker-php-ext-install amqp

RUN cp /usr/src/php/php.ini-production /usr/src/php/php.ini


