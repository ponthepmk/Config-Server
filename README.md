# Config-Server

# Install Phpmyadmin and mysql
     sudo apt update
     sudo apt install mysql-server mysql-client
     sudo apt install apache2

# Config Apache2
     sudo nano /etc/apache2/mods-enabled/dir.conf
          <IfModule mod_dir.c>
          DirectoryIndex index.html index.php index.xhtml index.htm
          </IfModule>
     sudo nano /etc/apache2/sites-enabled/000-default.conf
          <VirtualHost *:80>
               ServerAdmin admin@mylab.com
               DocumentRoot /var/www/html/
               ServerName example.com
               ServerAlias example.com

               ErrorLog ${APACHE_LOG_DIR}/error.log
               CustomLog ${APACHE_LOG_DIR}/access.log combined
          </VirtualHost>
     sudo systemctl restart apache2.service
     sudo apt-get install php php-cgi libapache2-mod-php php-common php-pear php-mbstring
