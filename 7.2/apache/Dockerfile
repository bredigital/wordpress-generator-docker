FROM php:7.2-apache

RUN apt-get update && apt-get install -y zlib1g-dev libzip-dev mariadb-client unzip \
	&& docker-php-ext-install mysqli pdo_mysql zip

RUN curl -L -o /usr/bin/wp https://raw.githubusercontent.com/wp-cli/builds/gh-pages/phar/wp-cli.phar \
	&& chmod +X /usr/bin/wp && chmod 766 /usr/bin/wp
RUN curl -L -o /usr/bin/composer https://getcomposer.org/composer-stable.phar  \
	&& chmod +X /usr/bin/composer && chmod 766 /usr/bin/composer

RUN curl -o /usr/src/generator.zip -fSL "https://github.com/bredigital/wordpress-generator/archive/master.zip?v=0" \
	&& unzip -q /usr/src/generator.zip -d /usr/src/ \
	&& cp -r /usr/src/wordpress-generator*/src/* /var/www/html \
	&& composer install -q --no-dev \
	&& chown www-data:www-data -R /var/www/html