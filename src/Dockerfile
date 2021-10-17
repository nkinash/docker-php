FROM php:fpm
RUN chmod 777 /var/www/
RUN apt-get update
RUN apt-get install -y \
    libzip-dev \
    zip \
    && docker-php-ext-configure zip \
    && docker-php-ext-install zip
RUN apt-get -y install \
        git \
        curl \
        g++ \
        libicu-dev \
        libmcrypt-dev \
        zlib1g-dev \
        libpq-dev \
        libldap2-dev \
        libfreetype6-dev \
        libjpeg62-turbo-dev \
        libxml2-dev \
        libmagickwand-dev \
        librabbitmq-dev \
        libpng-dev \
        nano \
        cron \
        --no-install-recommends

RUN docker-php-ext-install bcmath \
    && docker-php-ext-install ftp \
    && docker-php-ext-install xml \
    && docker-php-ext-install soap \
    && docker-php-ext-install pcntl \
    && docker-php-ext-install gd \
    # ext imap
    && apt-get install -y openssl \
    && docker-php-ext-install pdo_pgsql

################## CRON #############################
## Add crontab file in the cron directory
#ADD ./cron/crontab /etc/cron.d/app_cron
#
## Give execution rights on the cron job
#RUN chmod 0644 /etc/cron.d/app_cron \
#    && touch /var/log/cron.log
#
## Use the crontab file.
#RUN crontab /etc/cron.d/app_cron
######################################################
