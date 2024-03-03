## Objetivo
Can you find the flag in [file](https://jupiter.challenges.picoctf.org/static/fae9ac5267cd6e44124e559b901df177/strings) without running it?

## Pistas
[strings](https://linux.die.net/man/1/strings)

## Solución
El comando `strings` se usa para extraer texto legible de archivos binarios sin ejecutarlos. Al aplicarlo al archivo descargado y filtrar la salida con `grep` para "pico", se revela directamente la flag

```
arcf99-picoctf@webshell:~$ mkdir stringsIt
arcf99-picoctf@webshell:~$ cd stringsIt/
arcf99-picoctf@webshell:~/stringsIt$ wget https://jupiter.challenges.picoctf.org/static/fae9ac5267cd6e44124e559b901df177/strings
--2024-03-03 21:21:43--  https://jupiter.challenges.picoctf.org/static/fae9ac5267cd6e44124e559b901df177/strings
Resolving jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)... 3.131.60.8
Connecting to jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)|3.131.60.8|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 776032 (758K) [application/octet-stream]
Saving to: 'strings'

strings                                                  100%[=================================================================================================================================>] 757.84K  1.85MB/s    in 0.4s    

2024-03-03 21:21:43 (1.85 MB/s) - 'strings' saved [776032/776032]

arcf99-picoctf@webshell:~/stringsIt$ ls
strings
arcf99-picoctf@webshell:~/stringsIt$ strings strings | grep pico
picoCTF{5tRIng5_1T_7f766a23}
arcf99-picoctf@webshell:~/stringsIt$
```


## Notas adicionales

## Referencias