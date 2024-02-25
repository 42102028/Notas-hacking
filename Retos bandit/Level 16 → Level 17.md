# Objetivo
The credentials for the next level can be retrieved by submitting the password of the current level to **a port on localhost in the range 31000 to 32000**. First find out which of these ports have a server listening on them. Then find out which of those speak SSL and which don’t. There is only 1 server that will give the next credentials, the others will simply send back to you whatever you send to it.

# Datos de acceso al nivel
ssh bandit16@bandit.labs.overthewire.org -p 2220
JQttfApK4SeyHwDlI9SXGR50qclOAil1

# Solución
Con estos comandos obtenemos la llave
 ```
 nmap localhost -p 31000-32000 

 openssl s_client -connect localhost:31790
```

# Notas adicionales
 

# Referencias