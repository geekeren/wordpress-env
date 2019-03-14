FROM wordpress:5.1.1-php7.2-apache
RUN rm -rf /usr/src/wordpress
RUN apt-get update && apt-get install -y \
    libfreetype6-dev \
        libmcrypt-dev \
        libjpeg-dev \
        libpng-dev \
        zlib1g-dev \
        libapache2-mod-security2 \
    && pecl install mcrypt-1.0.2 \
    && docker-php-ext-install iconv mcrypt zip \
    && docker-php-ext-configure gd \
        --enable-gd-native-ttf \
        --with-freetype-dir=/usr/include/freetype2 \
        --with-png-dir=/usr/include \
        --with-jpeg-dir=/usr/include \
    && docker-php-ext-install gd \
    && docker-php-ext-install mbstring \
    && docker-php-ext-enable gd \
    && rm -rf /var/lib/apt/lists/*
RUN a2enmod ssl http2 headers security2