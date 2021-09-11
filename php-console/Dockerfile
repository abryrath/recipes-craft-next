FROM craftcms/cli:8.0-dev

# switch to the root user
USER root

RUN apk --update add --no-cache \
    re2c \
    lua-hashids \
    gmp-dev \
    git \
    bash
RUN docker-php-ext-configure gmp
RUN docker-php-ext-install gmp

COPY --from=composer:latest /usr/bin/composer /usr/local/bin/composer

USER www-data
