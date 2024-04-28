# NextCloud Admin

### PHP Upgrade from 8.0 to 8.2

[Reference#](https://tecadmin.net/switch-between-multiple-php-version-on-ubuntu/) 
[Reference](https://www.digitalocean.com/community/tutorials/how-to-run-multiple-php-versions-on-one-server-using-apache-and-php-fpm-on-centos-8)

[Reference2](https://php.watch/articles/install-php82-ubuntu-debian)
[Reference3](https://www.vetechno.in/how-to-uninstall-php-apache-and-mysql-on-ubuntu-20-04-lts/#First_we_remove_PHP_from_Ubuntu)

### Nextcloud Upgrade script 

Make sure that www-data is the owner for /var/www/nextcloud/ 

[Reference#](https://tecadmin.net/switch-between-multiple-php-version-on-ubuntu/](https://help.nextcloud.com/t/update-to-nextcloud-12-03-var-www-permissions-error/21243) 


```bash
sudo -u www-data php /var/www/nextcloud/updater/updater.phar
```
