FROM php:7.2-apache

RUN a2enmod rewrite

RUN apt-get update && apt-get install -y zlib1g-dev libzip-dev mariadb-client unzip \
	&& docker-php-ext-install mysqli pdo_mysql zip

RUN curl -L -o /usr/bin/wp https://raw.githubusercontent.com/wp-cli/builds/gh-pages/phar/wp-cli.phar \
	&& chown www-data:www-data /usr/bin/wp && chmod +X /usr/bin/wp && chmod 766 /usr/bin/wp

ENV GN_SYSTEM_WPCLI true
ENV GN_WPCLI        /usr/bin/wp

RUN curl -o /usr/src/generator.zip -fSL "https://github.com/bredigital/wordpress-generator/releases/download/1.3.1b/wordpress-generator-1.3.1b.zip" \
	&& mkdir /usr/src/generator \
	&& unzip -q /usr/src/generator.zip -d /usr/src/generator \
	&& cp -r /usr/src/generator/* /var/www/html \
	&& chown www-data:www-data -R /var/www/html \
	&& rm -r /usr/src/generator && rm /usr/src/generator.zip
