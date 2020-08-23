# Config-Server

## Install Phpmyadmin and mysql
     sudo apt update
     sudo apt install mysql-server mysql-client
     sudo apt install apache2

## Config Apache2
###### Step 1
     sudo nano /etc/apache2/mods-enabled/dir.conf
          <IfModule mod_dir.c>
          DirectoryIndex index.html index.php index.xhtml index.htm
          </IfModule>
###### Step 2
     sudo nano /etc/apache2/sites-enabled/000-default.conf
          <VirtualHost *:80>
               ServerAdmin admin@mylab.com
               DocumentRoot /var/www/html/
               ServerName example.com
               ServerAlias example.com

               ErrorLog ${APACHE_LOG_DIR}/error.log
               CustomLog ${APACHE_LOG_DIR}/access.log combined
          </VirtualHost>
###### Step 3
     sudo systemctl restart apache2.service
###### Step 4
     sudo apt-get install php php-cgi libapache2-mod-php php-common php-pear php-mbstring
###### Step 5
     sudo a2enconf php7.2-cgi
     sudo systemctl reload apache2.service
###### Step 6
     sudo apt-get install phpmyadmin php-gettext
