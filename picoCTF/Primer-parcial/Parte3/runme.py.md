## Objetivo
Run the `runme.py` script to get the flag. Download the script with your browser or with `wget` in the webshell.[Download runme.py Python script](https://artifacts.picoctf.net/c/34/runme.py)

## Pistas


## Solución
La solución implica descargar un script Python llamado `runme.py` desde una URL proporcionada, y luego ejecutar este script. Al ejecutar `runme.py`, se muestra directamente la flag: `picoCTF{run_s4n1ty_run}`

```
arcf99-picoctf@webshell:~$ mkdir runMe
arcf99-picoctf@webshell:~$ cd runMe/
arcf99-picoctf@webshell:~/runMe$ wget https://artifacts.picoctf.net/c/34/runme.py
--2024-03-03 22:13:53--  https://artifacts.picoctf.net/c/34/runme.py
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 3.160.22.92, 3.160.22.43, 3.160.22.128, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|3.160.22.92|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 270 [application/octet-stream]
Saving to: 'runme.py'

runme.py                                                 100%[=================================================================================================================================>]     270  --.-KB/s    in 0s      

2024-03-03 22:13:53 (152 MB/s) - 'runme.py' saved [270/270]

arcf99-picoctf@webshell:~/runMe$ ls
runme.py
arcf99-picoctf@webshell:~/runMe$ python runme.py 
picoCTF{run_s4n1ty_run}
```

## Notas adicionales

## Referencias