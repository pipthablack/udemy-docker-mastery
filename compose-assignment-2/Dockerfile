# Use the official Drupal 9 image
FROM drupal:9

# Install git, clean up after installation, and set up the Bootstrap theme
RUN apt-get update && apt-get install -y git \
    && rm -rf /var/lib/apt/lists/*

# Set the working directory to /var/www/html/themes
WORKDIR /var/www/html/themes

# Clone the Bootstrap theme and set the correct permissions
RUN git clone --branch 8.x-4.x --single-branch --depth 1 https://git.drupalcode.org/project/bootstrap.git \
    && chown -R www-data:www-data bootstrap

# Set the working directory back to /var/www/html
WORKDIR /var/www/html
