
C1:

![[Pasted image 20250304080031.png]]


Para docker, todos los comandos se ejecutan dentro del contenedor.

___
C2:
![[Pasted image 20250304085020.png]]

___
C3:
- Para verificar status de `dovecot`
`systemctl status dovecot`
`telnet <IP_addr> 110`: cannot connect through port 110 since its not active

- Para iniciar el servicio dovecot:
`systemctl start dovecot`


>[!info] para problemas conexion: sudo systemctl stop firewall. UNa vez acabada la practica sudo systemctl start firewall 


