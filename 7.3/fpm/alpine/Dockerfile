FROM php:7.3-fpm-alpine3.9

MAINTAINER Studio Visual <atendimento@studiovisual.com.br>

ENV CFLAGS="-I/usr/src/php"

RUN apk --update --no-cache add shadow git libpng-dev jpeg-dev libxml2-dev libxslt-dev libzip-dev freetype-dev rsync \
  postgresql-dev libxml2-dev zlib-dev icu-dev gettext-dev autoconf yarn automake libtool file build-base nasm musl openssh

COPY php.ini-development /usr/local/etc/php/php.ini

RUN docker-php-ext-configure gd --with-jpeg-dir=/usr/include/ --with-freetype-dir=/usr/include/

RUN docker-php-ext-configure intl --enable-intl

RUN docker-php-ext-install dom gd gettext hash intl json mbstring mysqli pdo pdo_mysql pdo_pgsql pgsql \
 phar posix simplexml soap xml xmlreader xmlrpc xmlwriter xsl zip

RUN usermod -u 1000 www-data && groupmod -g 1000 www-data

RUN find / -group 82 -exec chgrp -h www-data {} \; && find / -user 82 -exec chown -h www-data {} \;

COPY --from=composer:2.0 /usr/bin/composer /usr/bin/composer

EXPOSE 9000

ENV NVM_DIR /usr/local/nvm

RUN curl -o- https://raw.githubusercontent.com/creationix/nvm/v0.33.1/install.sh | bash

ENV NODE_VERSION v7.9.0

RUN /bin/bash -c "source $NVM_DIR/nvm.sh && nvm install $NODE_VERSION && nvm use --delete-prefix $NODE_VERSION"

ENV NODE_PATH $NVM_DIR/versions/node/$NODE_VERSION/lib/node_modules

ENV PATH      $NVM_DIR/versions/node/$NODE_VERSION/bin:$PATH

CMD ["php-fpm"]