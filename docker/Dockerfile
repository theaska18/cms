# Gunakan image resmi PHP dengan Apache
#FROM php:8.0-apache
FROM arm64v8/php:7.2-apache
RUN ls -l
# Instal ekstensi PHP yang dibutuhkan CodeIgniter 
RUN docker-php-ext-install mysqli pdo pdo_mysql
#RUN apt-get update
RUN ls -l

# Salin file konfigurasi
COPY docker/php.ini /usr/local/etc/php/
COPY docker/sites.conf /etc/apache2/sites-available/000-default.conf

# Aktifkan mod_rewrite untuk Apache
RUN a2enmod rewrite

# Set direktori kerja

RUN ls -l

# Salin aplikasi ke dalam container
RUN chown -R www-data:www-data /var/www/html
COPY app/ /var/www/html/
WORKDIR /var/www/html
# Set hak akses


# Expose port 80 untuk akses HTTP
EXPOSE 80