FROM php:7.3.9-cli-alpine

ARG BUILD_ENVIRONMENT

RUN apk update \
    && apk add --no-cache curl g++ make autoconf bash supervisor

RUN if [ "${BUILD_ENVIRONMENT}" = "development" ]; then \
    docker-php-source extract \
    && pecl install xdebug mongodb \
    && docker-php-ext-enable xdebug mongodb \
    && docker-php-source delete; \
fi

RUN if [ "${BUILD_ENVIRONMENT}" = "release" ]; then \
    docker-php-source extract \
    && pecl install mongodb \
    && docker-php-ext-enable mongodb \
    && docker-php-source delete; \
fi

RUN docker-php-ext-install mysqli bcmath \
    && curl -sS https://getcomposer.org/installer | php -- --install-dir=/usr/local/bin --filename=composer

RUN rm -rf /tmp/*

COPY ./config/php/supervisord.conf /etc/supervisord.conf

CMD ["/usr/bin/supervisord", "-c", "/etc/supervisord.conf"]