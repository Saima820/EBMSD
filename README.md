# Environment Setup for Linux.
# 1. How to Install Nginx, MySQL, PHP (LEMP Stack) on Ubuntu 24.04
# Nginx
1. Install Nginx
   $ sudo apt install nginx -y
2. Start Nginx
   $ sudo systemctl start nginx
3. Enable Nginx to start at boot time.
   $ sudo systemctl enable nginx
4. View the Nginx service status and verify that it's active on your server.
   $ sudo systemctl status nginx
# MySQL
1. Install the latest MySQL database server package on your server.
   $ sudo apt install mysql-server -y
2. Start the MySQL service.
   $ sudo systemctl start mysql
3. Enable the MySQL service to start at boot time.
   $ sudo systemctl enable mysql
4.View the MySQL service status and verify that it's active on the server.
   $ sudo systemctl status mysql
5. Start the MySQL secure installation script to disable insecure default configurations.
   $ sudo mysql_secure_installation
* Enter Y when prompted to enable the VALIDATE PASSWORD component that ensures strict password policies for the database users.
6. Access the MySQL console to set up a new root user password.
   $ sudo mysql
7. Modify the root user with a strong password and enable mysql_native_password as the default authentication method.
   mysql> ALTER USER 'root'@'localhost' IDENTIFIED WITH mysql_native_password BY 'secured_password';
8. Reload the MySQL Privilege tables to apply changes.
   mysql> FLUSH PRIVILEGES;
9. Exit the MySQL console.
   mysql> exit
10. Restart the MySQL database server.
   $ sudo systemctl restart mysql
# PHP
1. Install PHP and PHP-FPM on your server.
   $ sudo apt install php php-fpm -y
2. Install essential PHP modules required by most dynamic applications.
   $ sudo apt install php-mysql php-cli -y
3. View the installed PHP version on your server.
   $ php -v
4. Start the PHP-FPM service depending on your installed version such as PHP 8.3.
   $ sudo systemctl start php8.3-fpm
5. Enable PHP-FPM to start at boot time.
   $ sudo systemctl enable php8.3-fpm
6. View the PHP-FPM service status and verify that it's running.
   $ sudo systemctl status php8.3-fpm
# Workbench
1. Update the System
   sudo apt update
   sudo apt upgrade -y
2. Install MySQL Workbench
   sudo apt install mysql-workbench -y
3. Verify Installation
   mysql-workbench --version
4. Launch MySQL Workbench
   mysql-workbench
* Alternate Method: Install from MySQL APT Repository
1. Download and Add the MySQL APT Repository:
   wget https://dev.mysql.com/get/mysql-apt-config_0.8.26-1_all.deb
   sudo dpkg -i mysql-apt-config_0.8.26-1_all.deb
   sudo apt update
2. Install MySQL Workbench:
   sudo apt install mysql-workbench-community -y
Note: If you're getting the "unable to locate package mysql-workbench" error, it might be because the MySQL Workbench package is not available in the default Ubuntu repositories. You can resolve this by using the official MySQL APT repository.Here are the steps to install MySQL Workbench on Ubuntu:
1. Add MySQL APT Repository
   wget https://dev.mysql.com/get/mysql-apt-config_0.8.26-1_all.deb
   sudo dpkg -i mysql-apt-config_0.8.26-1_all.deb
2. Update Your Package List
   sudo apt update
3. Install MySQL Workbench
   sudo apt install mysql-workbench-community
4. Launch MySQL Workbench
   mysql-workbench
# Composer
1. Install Dependencies
   $ sudo apt update
   $ sudo apt install php-cli unzip
2. Download and Install Composer
   $ cd ~
   $ curl -sS https://getcomposer.org/installer -o /tmp/composer-setup.php
   $ HASH=`curl -sS https://composer.github.io/installer.sig`
   $ php -r "if (hash_file('SHA384', '/tmp/composer-setup.php') === '$HASH') { echo 'Installer verified'; } else { echo 'Installer corrupt'; unlink('composer-setup.php'); } echo PHP_EOL;"
   $ sudo php /tmp/composer-setup.php --install-dir=/usr/local/bin --filename=composer
   $ composer


 




