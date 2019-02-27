FROM php:7.2.13

# docker build -t licunchang/php:7.2.13 .

RUN apt-get update \
  && apt-get install -y git curl unzip zip libpng-dev --no-install-recommends \
  && rm -rf /var/lib/apt/lists/* \
  && php -r "copy('https://getcomposer.org/installer', 'composer-setup.php');" \
  && php -r "if (hash_file('sha384', 'composer-setup.php') === '48e3236262b34d30969dca3c37281b3b4bbe3221bda826ac6a9a62d6444cdb0dcd0615698a5cbe587c3f0fe57a54d8f5') { echo 'Installer verified'; } else { echo 'Installer corrupt'; unlink('composer-setup.php'); } echo PHP_EOL;" \
  && php composer-setup.php --install-dir=/usr/local/bin --filename=composer \
  && php -r "unlink('composer-setup.php');" \
  && curl -L https://cs.symfony.com/download/php-cs-fixer-v2.phar -o /usr/local/bin/php-cs-fixer \
  && chmod a+x /usr/local/bin/php-cs-fixer \
  && curl -L https://squizlabs.github.io/PHP_CodeSniffer/phpcs.phar -o /usr/local/bin/phpcs \
  && chmod a+x /usr/local/bin/phpcs \
  && curl -L https://squizlabs.github.io/PHP_CodeSniffer/phpcbf.phar -o /usr/local/bin/phpcbf \
  && chmod a+x /usr/local/bin/phpcbf \
  && curl -L http://static.phpmd.org/php/latest/phpmd.phar -o /usr/local/bin/phpmd \
  && chmod a+x /usr/local/bin/phpmd \
  && curl -L https://github.com/phpstan/phpstan/releases/download/0.11.1/phpstan.phar -o /usr/local/bin/phpstan \
  && chmod a+x /usr/local/bin/phpstan \
  && docker-php-ext-install -j$(nproc) gd \
  && docker-php-ext-install -j$(nproc) bcmath opcache pdo_mysql zip \
  && pecl install ast-1.0.0 \
  && docker-php-ext-enable ast \
  && curl -L https://github.com/phan/phan/releases/download/1.2.0/phan.phar -o /usr/local/bin/phan \
  && chmod a+x /usr/local/bin/phan \
  && curl -L https://phar.phpunit.de/phpunit-8.phar -o /usr/local/bin/phpunit \
  && chmod a+x /usr/local/bin/phpunit
