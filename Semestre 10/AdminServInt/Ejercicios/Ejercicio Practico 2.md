- Implementar MTA simple
- Configurar MAA a traves del protocolo IMAP

```bash
sudo yum install sendmail sendmail-cf
# sudo yum install epel-release
sudo nano /etc/mail/sendmail.mc
```

![[C1_1.png]]

![[C1_2.png]]

```
sudo cp /etc/mail/sendmail.mc . #Copia archivo a directorio actual
sudo chown gael:gael sendmail.mc #Cambia permisos del archivo copiado a nuestro usuario

ls -la # podemos ver los cambios de permisos
```

```
sudo m4 /etc/mail/sendmail.mc > /etc/mail/sendmail.cf

ls -la /etc/mail/sendmail.cf # Vemos los cambios realizados
```

```bash
cat /etc/hostname # Verificamos que el nombre del host sea correcto

sudo nano /etc/mail/local-host-name # COnfiguramos nuestro nombre de host

sudo nano /etc/mail/access # Habilitamos el acceso al servicio
```

![[Universidad/Semestre 10/AdminServInt/Ejercicios/imgs_ej1/C2.png]]


```bash
cp /etc/mail/access . #Copiamos el archivo modificado
chown gael:gael access # MOdificamos permiso a nuestro usuario al archivo modificado
ls -la # POdemos verificar cambios de permisos al archivo copiado
```

- Con estas configuraciones ya tenemos nuestro SMTP y MTA
	- Pero estos solo pueden enviar mensajes
- Debemos ahora crear el IMAP y MAA

```bash
sudo yum install dovecot  #Se instala Dovecot

#ELiminamos el software postfix para evitar problemas de config
rpm -qa | grep postfix # Buscamos si hay algo instalado que lleve postfix en nombre
sudo yum remove postfix # ELiminamos el software postfix

sudo nano /etc/dovecot/dovecot.conf # COnfiguramos protocolos de dovecot
```


![[Semestre 10/AdminServInt/Ejercicios/imgs_ej1/C3.png]]

```bash
sudo cp /etc/dovecot/dovecot.conf . #Hacemos copia de configuracion
sudo chown gael:gael dovecot.conf # cambiamos permisos del archivo copiado
```

![[Semestre 10/AdminServInt/Ejercicios/imgs_ej1/C4.png]]

Hacemos copia del archivo y cambiamos sus permisos

![[Semestre 10/AdminServInt/Ejercicios/imgs_ej1/C5.png]]

Hacemos copia y cambiamos permisos


```bash
sudo systemctl start sendmail #Se inicia sendmaail
sudo systemctl start dovecot # Inicia dovecot
```

Para enviar correos:
```bash
sudo su # Se accesa a root

```

![[Semestre 10/AdminServInt/Ejercicios/imgs_ej1/C6.png]]

![[C7_1.png]]

![[C7_2.png]]

EN la terminal se puede observar el contenido del correo, tanto las cabeceras de MIME, como los metadatos y el dato enviado en si 

___

- Configuracion sendmail
- cp -> copy archivos
- chown -> change owner
- root -> superuser do