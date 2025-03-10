
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

___
# 3.4

`disable`: permite que, al iniciar la maquina, el servicio telnet no se inicie automaticamente. 

C5:
![[Semestre 10/AdminServInt/Ejercicios/Imgs_ej2/C5.png]]

___
# 4.
cliente SSH -> servidor SSH

C6:
![[Semestre 10/AdminServInt/Ejercicios/Imgs_ej2/c6.png]]

## 4.3

C7:
![[C7.png]]


## 4.4 Tuneles

EL punto 2. los corchetes son opcionales y solo se utilizan en docker.




## Jaulas

Al usar Docker, las jaulas no son necesarias, ya que por la configuracion de docker, este aisla mediante el contenedor, haciendo un simil a una jaula



C9:
`ssh -L <puerto>:localhost:110 user@IP`
`ssh -L <puerto>:localhost:143 user@IP`

ENtregable: 13 marzo