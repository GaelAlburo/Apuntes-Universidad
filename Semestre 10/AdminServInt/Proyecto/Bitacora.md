# Packages


# NGINX
```{Bash}
sudo dnf install nginx

sudo 
```

ref: https://howtoforge.es/como-instalar-nextcloud-con-nginx-y-php-7-3-en-centos-8/


## MariaDB

root password = pass1234


___
## Configurar PHP-FPM

- nano /etc/php.ini
valores originales:
memory_limit = 128M
;date.timezone=
cgi.fixpathinfo = 0

- nano /etc/php.d/10-opcache.ini
opcache.enable=1
;opcache.interned_strings_buffer=8
;opcache.max_accelerated_files=10000
;opcache.memory_consumption=128  
;opcache.save_comments=1  
;opcache.revalidate_freq=2

- nano /etc/php-fpm.d/www.conf
user = apache
group = apache
listen = /run/php-fpm/www.sock
;env[HOSTNAME] = $HOSTNAME  
;env[PATH] = /usr/local/bin:/usr/bin:/bin  
;env[TMP] = /tmp  
;env[TMPDIR] = /tmp  
;env[TEMP] = /tmp
;php_value[opcache.file_cache] = /var/lib/php/opcache


___

## SSL Letsencrypt

email: gael.a24@outlook.com
domain: swiftsharesproject.pw


____
## Nextcloud

![[Pasted image 20250501185600.png]]

![[Pasted image 20250501190352.png]]



____
## SSL

![[Pasted image 20250505213046.png]]

