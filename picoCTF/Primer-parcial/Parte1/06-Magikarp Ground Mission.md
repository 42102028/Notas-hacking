## Objetivo
Do you know how to move between directories and read files in the shell? Start the container, `ssh` to it, and then `ls` once connected to begin. Login via `ssh` as `ctf-player` with the password, `b60940ca`

Additional details will be available after launching your challenge instance.

## Pistas
Finding a cheatsheet for bash would be really helpful!

## Solución

1. **Iniciar sesión en el servidor** usando SSH.
2. **Listar los archivos en el directorio actual** y encontrar `1of3.flag.txt` e `instructions-to-2of3.txt`.
3. **Leer el contenido de `1of3.flag.txt`**, que contiene la primera parte de la flag: `picoCTF{xxsh_`.
4. **Movernos por el sistema de archivos** para encontrar las otras partes de la flag.
5. **Encontrar y leer `3of3.flag.txt`** en otro directorio, que contiene la tercera parte de la flag: `c1754242}`.
6. **Buscar y encontrar `2of3.flag.txt`** que contiene la segunda parte de la flag: `0ut_0f_\/\/4t3r_`.

Al combinar las tres partes de la flag en el orden correcto, se obtiene la flag complet

```
arcf99-picoctf@webshell:~$ ssh ctf-player@venus.picoctf.net -p 55241
ctf-player@venus.picoctf.net's password: 
Welcome to Ubuntu 18.04.5 LTS (GNU/Linux 5.4.0-1041-aws x86_64)

 * Documentation:  https://help.ubuntu.com
 * Management:     https://landscape.canonical.com
 * Support:        https://ubuntu.com/advantage
This system has been minimized by removing packages and content that are
not required on a system that users do not log into.

To restore this content, you can run the 'unminimize' command.
Last login: Sun Mar  3 20:36:17 2024 from 127.0.0.1
ctf-player@pico-chall$ ls
1of3.flag.txt  instructions-to-2of3.txt
ctf-player@pico-chall$ cat 1of3.flag.txt 
picoCTF{xxsh_
ctf-player@pico-chall$ ls
1of3.flag.txt  instructions-to-2of3.txt
ctf-player@pico-chall$ cd ..
ctf-player@pico-chall$ ls
3of3.flag.txt  drop-in
ctf-player@pico-chall$ cat 3of3.flag.txt 
c1754242}
ctf-player@pico-chall$ cd ..
ctf-player@pico-chall$ ls
ctf-player
ctf-player@pico-chall$ cd ..
ctf-player@pico-chall$ ls
2of3.flag.txt  bin  boot  dev  etc  home  instructions-to-3of3.txt  lib  lib64  media  mnt  opt  proc  root  run  sbin  srv  sys  tmp  usr  var
ctf-player@pico-chall$ cat 2of3.flag.txt 
0ut_0f_\/\/4t3r_
ctf-player@pico-chall$ 
 
 
```

## Notas adicionales

## Referencias



