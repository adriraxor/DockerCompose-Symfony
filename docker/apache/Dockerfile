FROM php:8.0.13-apache
RUN curl -OL https://github.com/composer/composer/releases/download/2.3.10/composer.phar
RUN mv composer.phar /usr/local/bin/composer
RUN chmod +x /usr/local/bin/composer && a2enmod rewrite && service apache2 restart
RUN apt-get update && apt-get install -y nano
RUN apt-get install -y  git
RUN git config --global user.email "default@gmail.com"
RUN git config --global user.name "default"
RUN apt-get install -y wget
RUN wget https://get.symfony.com/cli/installer -O - | bash
RUN mv /root/.symfony5/bin/symfony /usr/local/bin/symfony
RUN docker-php-ext-install pdo_mysql
RUN apt-get install -y zip
RUN apt-get install -y zlib1g-dev libicu-dev g++
RUN docker-php-ext-configure intl
RUN docker-php-ext-install intl
RUN mkdir -p /var/run/apache2/
RUN apt install nodejs npm -y
RUN npm cache clean -f
RUN npm install -g n
RUN n stable
