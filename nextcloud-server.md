# Nextcloud (Serveur)
## Installation
### Paquets
    sudo apt install apache2 mariadb-server libapache2-mod-php5 php5-gd php5-json php5-mysql php5-curl php5-intl php5-mcrypt php5-imagick

### Télécharger Nextcloud
    wget https://download.nextcloud.com/server/releases/nextcloud-X.X.X.zip

### Extraire l'archive
    unzip nextcloud-X.X.X.zip

### Droits : www-data
    chown -R www-data:www-data nextcloud/

## Apache 2
Créer le fichier de configuration de Nexcloud :

    sudo vi /etc/apache2/sites-available/nextcloud.conf

Copier ces lignes :

    <VirtualHost *:80>
     DocumentRoot "/var/www/nextcloud"
     ServerName nextcloud.your-domain.com

     ErrorLog ${APACHE_LOG_DIR}/error.log
     CustomLog ${APACHE_LOG_DIR}/access.log combined

    <Directory /var/www/nextcloud/>
     Options +FollowSymlinks
     AllowOverride All

     <IfModule mod_dav.c>
     Dav off
     </IfModule>

     SetEnv HOME /var/www/nextcloud
     SetEnv HTTP_HOME /var/www/nextcloud
     Satisfy Any

    </Directory>

    </VirtualHost>

Créer un lien symbolique pour activer Nextcloud :

    sudo ln -s /etc/apache2/sites-available/nextcloud.conf /etc/apache2/sites-enabled/nextcloud.conf

Activer les modules Apaches 2 nécessaires :

    sudo a2enmod rewrite
    sudo a2enmod headers
    sudo a2enmod env
    sudo a2enmod dir
    sudo a2enmod mime
    sudo a2enmod setenvif

Redémarrer Apache 2 :

    sudo service apache2 restart

## MariaDB
Logguer à MariaDB :

    mysql -u root -p

Créer une base de données :

    CREATE DATABASE nextcloud;

Créer un nouvel utilisateur :

    CREATE USER nextclouduser@localhost IDENTIFIED BY 'your-password';

Droits sur la base de données nextcloud :

    GRANT ALL PRIVILEGES ON nextcloud.* TO nextcloud@localhost IDENTIFIED BY 'your-password';

MAJ des droits :
    FLUSH PRIVILEGES;

Sortir de MariaDB :

    exit;

## Nextcloud
Allez sur l'adresse http://nextcloud.your-domain.com et compléter les champs pour installer le serveur Nextcloud
