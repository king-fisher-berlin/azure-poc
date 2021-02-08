FROM php:7.3-apache

# Install PHP Extensions
# Available names: bcmath bz2 calendar ctype curl dba dom enchant exif fileinfo filter ftp gd gettext gmp hash iconv imap
# interbase intl json ldap mbstring mysqli oci8 odbc opcache pcntl pdo pdo_dblib pdo_firebird pdo_mysql pdo_oci pdo_odbc
# pdo_pgsql pdo_sqlite pgsql phar posix pspell readline recode reflection session shmop simplexml snmp soap sockets sodium
# spl standard sysvmsg sysvsem sysvshm tidy tokenizer wddx xml xmlreader xmlrpc xmlwriter xsl zend_test zip
RUN apt-get update && apt-get install -y zlib1g-dev libicu-dev g++ npm git sudo vim
RUN docker-php-ext-configure intl
RUN docker-php-ext-install intl bcmath pdo_mysql sysvsem
RUN apt-get install -y libxml2-dev
RUN apt-get install -y libzip-dev unzip libpng-dev libgpgme11-dev
RUN docker-php-ext-install soap zip gd
RUN docker-php-ext-install mysqli
RUN docker-php-ext-install opcache
RUN pecl install \
    gnupg
RUN docker-php-ext-enable \
    gnupg
