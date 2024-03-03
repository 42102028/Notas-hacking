## Objetivo
Can you find the flag in [file](https://jupiter.challenges.picoctf.org/static/515f19f3612bfd97cd3f0c0ba32bd864/file)? This would be really tedious to look through manually, something tells me there is a better way.

## Pistas
grep [tutorial](https://ryanstutorials.net/linuxtutorial/grep.php)
## Solución
La solución consiste en descargar un archivo llamado `file`, y luego usar el comando `grep` para buscar dentro de ese archivo cualquier línea que contenga la cadena "pico". Al hacerlo, se encuentra la flag: `picoCTF{grep_is_good_to_find_things_5af9d829}`
```
arcf99-picoctf@webshell:~$ mkdir firstGrep
arcf99-picoctf@webshell:~$ cd firstGrep/
arcf99-picoctf@webshell:~/firstGrep$ wget https://jupiter.challenges.picoctf.org/static/515f19f3612bfd97cd3f0c0ba32bd864/file
--2024-03-03 21:13:28--  https://jupiter.challenges.picoctf.org/static/515f19f3612bfd97cd3f0c0ba32bd864/file
Resolving jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)... 3.131.60.8
Connecting to jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)|3.131.60.8|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 14551 (14K) [application/octet-stream]
Saving to: 'file'

file                                                     100%[=================================================================================================================================>]  14.21K  --.-KB/s    in 0s      

2024-03-03 21:13:28 (151 MB/s) - 'file' saved [14551/14551]

arcf99-picoctf@webshell:~/firstGrep$ ls
file
arcf99-picoctf@webshell:~/firstGrep$ cat file | grep pico
picoCTF{grep_is_good_to_find_things_5af9d829}
```

## Notas adicionales

## Referencias