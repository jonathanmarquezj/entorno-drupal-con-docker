# Comando a ejecutar para crear la imagen
# docker build -t "jonathan-drupal" .

# Arrancar
# docker run -d --name drupal jonathan-drupal

FROM drupal:8.9.13-php7.4-fpm-buster as base


## Aditional packages for day-2 operations
RUN apt-get update && \
    DEBIAN_FRONTEND=noninteractive apt-get install --no-install-recommends -y \
    unzip \
    git \
    vim \
    sudo \
    openssh-server \
    rsync \
    default-mysql-client \
	libfcgi-bin \
    openssh-client && \
    apt-get clean -y && \
    apt-get autoclean -y && \
    apt-get autoremove -y && \
    rm -rf /var/lib/{apt,dpkg,cache,log}/ && \
    rm -rf /var/lib/apt/lists/*


WORKDIR /var/www/html

EXPOSE 9000


CMD ["php-fpm","--fpm-config","/usr/local/etc/php-fpm.conf","-c","/usr/local/etc/php/php.ini"]