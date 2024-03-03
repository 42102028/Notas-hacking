## Objetivo
Using netcat (nc) is going to be pretty important. Can you connect to `jupiter.challenges.picoctf.org` at port `41120` to get the flag?

## Pistas
nc [tutorial](https://linux.die.net/man/1/nc)

## Solución
La solución consiste en utilizar el comando `nc` (netcat) para conectarse a un servidor en la dirección `jupiter.challenges.picoctf.org` en el puerto `41120`. Al establecer la conexión, el servidor envía un mensaje de felicitación y revela la flag: `picoCTF{nEtCat_Mast3ry_3214be47}`. 
```
arcf99-picoctf@webshell:~$ mkdir whatsAnetCat
arcf99-picoctf@webshell:~$ cd whatsAnetCat/
arcf99-picoctf@webshell:~/whatsAnetCat$ nc jupiter.challenges.picoctf.org 41120
You're on your way to becoming the net cat master
picoCTF{nEtCat_Mast3ry_3214be47}
```

## Notas adicionales
Netcat es una utilidad de red que se puede usar para leer y escribir datos a través de conexiones de red usando el protocolo TCP o UDP, demostrando su uso para recibir información directamente de servidores remotos

## Referencias