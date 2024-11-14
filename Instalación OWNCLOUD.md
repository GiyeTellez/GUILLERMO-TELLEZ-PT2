<h1>Instalación Owncloud</h1>
<ol>
    <li>"sudo apt update"</li>
    <li>"sudo apt upgrade"</li>
    <li>"sudo apt install -y apache2"</li>
    <li>"sudo apt install -y mysql-server"</li>
    <li>"sudo apt install -y php libapache2-mod-php"</li>
    <li>"sudo apt install -y php-fpm php-common php-mbstring php-xmlrpc php-soap php-gd php-xml php-intl php-mysql php-cli php-ldap php-zip php-curl"</li>
    <li>"sudo systemctl restart apache2"</li>
    <li>"sudo mysql"</li>
    <li>"CREATE DATABASE bbdd;"</li>
    <li>"CREATE USER 'usuario'@'localhost' IDENTIFIED WITH mysql_native_password BY 'password';"</li>
    <li>"GRANT ALL ON bbdd.* to 'usuario'@'localhost';"</li>
    <li>"exit"</li>
    <li>"mysql -u usuario -p"</li>
    <li>"sudo cp ~/Descargas/"Nombre del archivo" /var/www/html</li>
    <li>"cd /var/www/html"</li>
    <li>"sudo unzip "Nombre del archivo"</li>
    <li>"sudo cp -R "Nombre de la carpeta"/. /var/www/html"</li>
    <li>"sudo rm -rf "Nombre de la carpeta"/"</li>
    <li>"sudo rm -rf /var/www/html/index.html"</li>
    <li>"cd /var/www/html"</li>
    <li>"sudo chmod -R 775 ."</li>
    <li>"sudo chown -R usuario:www-data ."</li>
</ol>
<h1>Instalación Versión 7.4 de PHP a Ubuntu 24.04</h1>
<ol>
    <li>"sudo apt install software-properties-common -y"</li>
    <li>"LC_ALL=C.UTF-8 sudo add-apt-repository ppa:ondrej/php -y"</li>
    <li>"sudo apt update"</li>
    <li>"sudo apt install php7.4 -y"</li>
    <li>"sudo apt install -y php libapache2-mod-php7.4"</li>
    <li>"sudo apt install -y php7.4-fpm php7.4-common php7.4-mbstring php7.4-xmlrpc php7.4-soap php7.4-gd php7.4-xml php7.4-intl php7.4-mysql php7.4-cli php7.4-ldap php7.4-zip php7.4-curl"</li>
    <li>"sudo update-alternatives --config php"</li>
    <li>"sudo a2enmod proxy_fcgi setenvif"</li>
    <li>"sudo a2enconf php7.4-fpm"</li>
    <li>"sudo service apache2 restart"</li>
</ol>
