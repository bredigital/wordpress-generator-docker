FROM php:7.2-apache

RUN apt-get update && apt-get install -y zlib1g-dev libzip-dev mariadb-client unzip \
	&& docker-php-ext-install mysqli pdo_mysql zip

RUN curl https://raw.githubusercontent.com/wp-cli/builds/gh-pages/phar/wp-cli.phar --output /usr/bin/wp \
	&& chmod +X /usr/bin/wp && chmod 766 /usr/bin/wp

RUN curl -o /usr/src/generator.zip -fSL "https://github.com/bredigital/wordpress-generator/releases/download/1.1b/wordpress-generator-1.1b.zip" ; \
	unzip /usr/src/generator.zip -d /var/www/html; \
	rm /usr/src/generator.zip