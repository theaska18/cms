# Gunakan image resmi PHP dengan Apache
FROM php:8.1-apache

# Instal ekstensi PHP yang dibutuhkan CodeIgniter
#RUN docker-php-ext-install mysqli pdo pdo_mysql

# Salin file konfigurasi
COPY docker/php.ini /usr/local/etc/php/
COPY docker/sites.conf /etc/apache2/sites-available/000-default.conf

# Aktifkan mod_rewrite untuk Apache
#RUN a2enmod rewrite

# Set direktori kerja
WORKDIR /var/www/html

# Salin aplikasi ke dalam container
COPY app/ /var/www/html/

# Set hak akses
RUN chown -R www-data:www-data /var/www/html

# Expose port 80 untuk akses HTTP
EXPOSE 80