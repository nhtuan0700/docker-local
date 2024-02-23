FROM php:8.2-fpm

WORKDIR /var/www/html

RUN apt-get update && \
    apt-get upgrade -y && \
    # zlib1g-dev libzip-dev(pcntl) libpng-dev(pdo_mysql)
    apt-get install -y git libzip-dev libpng-dev  \
    # pcntl: create and manage multiple processes within a single PHP script
    # gd: a graphics software library for dynamically manipulating images
    && docker-php-ext-install pcntl zip pdo_mysql gd

# Cli tool for transfering data with URLs, here it's used for download Composer, 
# specifying the installation directory and the filename for the Composer executable.
# Explain:
# -s: silent mode (not show progress or error message)
# -S: show error if they occur
# php -- --install-dir=/usr/local/bin --filename=composer:
# - this part of command runs `php` and passes downloaded installer script to it
# - The double `--` are used to seperate the argument passed to PHP from arguments passed to Composer installer script
#   + --install-dir=/usr/local/bin: specifies the directory where composer will be installed
#   + --filename=composer: specifies the file name for the Composer executable
RUN curl -sS https://getcomposer.org/installer | php -- --install-dir=/usr/local/bin --filename=composer

COPY . .
