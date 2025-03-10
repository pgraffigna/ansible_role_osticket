### actualizar version
```shell
# backup de osticket
tar -czf ~/osticket_cultura.tar.gz /var/www/osticket

# descargar nueva version
wget -q https://github.com/osTicket/osTicket/releases/download/v1.16.3/osTicket-v1.16.3.zip

# descomprimir en /var/www
sudo unzip osTicket-v1.16.3.zip -d /var/www/osticket/

# instalar php 8.0
sudo add-apt-repository ppa:ondrej/php

# instalando dependencias php
sudo apt install -y php8.0-{common,fpm,imap,apcu,intl,cgi,mbstring,gd,mysql,bcmath,xml,ldap}

# activando modulos
sudo a2enmod proxy_fcgi setenvif
sudo a2enconf php8.0-fpm

# activar servicio apache
sudo systemctl reload apache2.service
sudo systemctl restart apache2
```
#### exportar/importar db
```sql
> mysqldump --opt -u root -p osticket_db > ~/osticket_backup.sql
> mysqldump --opt -u root -p osticket_db < ~/osticket_backup.sql
```
