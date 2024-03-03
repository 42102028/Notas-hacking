## Objetivo
Sometimes you need to handle process data outside of a file. Can you find a way to keep the output from this program and search for the flag? Connect to `jupiter.challenges.picoctf.org 4427`.

## Pistas
1. Remember the flag format is picoCTF{XXXX}
2. What's a pipe? No not that kind of pipe... This [kind](http://www.linfo.org/pipes.html)

## Solución
En este proceso, se conecta al servidor `jupiter.challenges.picoctf.org` en el puerto `4427` usando `nc` (netcat) y se redirige la salida a un archivo llamado `contra`. Luego, al utilizar el comando `grep` para filtrar el contenido del archivo `contra` por la cadena "pico", se encuentra y se muestra la flag

![[Pasted image 20240303163306.png]]

## Notas adicionales

## Referencias
[All about pipes, by The Linux Information Project (LINFO)](https://www.linfo.org/pipes.html)