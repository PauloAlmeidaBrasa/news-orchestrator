# Use the official PHP 8.2 image
FROM php:8.2-cli

# Set working directory
WORKDIR /app

# Install system dependencies
RUN apt-get update && apt-get install -y \
    git \
    curl \
    libpng-dev \
    libonig-dev \
    libxml2-dev \
    zip \
    unzip \
    libzip-dev \
    libicu-dev \
    libpq-dev \
    libfreetype6-dev \
    libjpeg62-turbo-dev \
    libwebp-dev \
    libxpm-dev

# Clear cache
RUN apt-get clean && rm -rf /var/lib/apt/lists/*

# Install PHP extensions
RUN docker-php-ext-install pdo_mysql mbstring exif pcntl bcmath gd intl zip opcache

# Configure GD library
RUN docker-php-ext-configure gd --with-freetype --with-jpeg --with-webp --with-xpm

# Install Composer
COPY --from=composer:latest /usr/bin/composer /usr/bin/composer

#COPY composer.json ../../docker/admin-back-news-service
# Copy existing application directory contents
COPY . .  

# Install Laravel dependencies
RUN composer install --ignore-platform-reqs

# Generate Laravel key
RUN php artisan key:generate

# Set permissions for Laravel storage and bootstrap cache
RUN chown -R www-data:www-data /var/www/html/storage /var/www/html/bootstrap/cache

# Expose port 8000 (default for php artisan serve)
EXPOSE 8000

# Start the Laravel development server
CMD ["php", "artisan", "serve", "--host=0.0.0.0", "--port=8000"]