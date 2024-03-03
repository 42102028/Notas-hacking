## Objetivo
Can you crack the password to get the flag?Download the password checker [here](https://artifacts.picoctf.net/c/15/level2.py) and you'll need the encrypted [flag](https://artifacts.picoctf.net/c/15/level2.flag.txt.enc) in the same directory too.

## Pistas
1. Does that encoding look familiar?
2. The `str_xor` function does not need to be reverse engineered for this challenge.
## Solución
La solución al desafío implica descargar un script de Python (`level2.py`) y un archivo cifrado (`level2.flag.txt.enc`) en el directorio `pwCrack2`. Al ejecutar `level2.py`, se solicita una contraseña para acceder a la flag. Tras un intento fallido con una contraseña incorrecta, se revisa el código en `level2.py` usando `nano`, donde se descubre la función `level_2_pw_check` que compara la contraseña ingresada con una combinación específica de caracteres obtenidos a través de la función `chr()` con valores hexadecimales.

Analizando el código, se identifica que la contraseña correcta es la concatenación de los caracteres Unicode correspondientes a los valores hexadecimales `0x33`, `0x39`, `0x63`, y `0x65`, que resultan en `39ce`. Al ejecutar nuevamente `level2.py` e ingresar `39ce` como contraseña, se desencripta y revela la flag: `picoCTF{tr45h_51ng1ng_502ec42e}`.

```
arcf99-picoctf@webshell:~$ mkdir pwCrack2
arcf99-picoctf@webshell:~$ cd pwCrack2
arcf99-picoctf@webshell:~/pwCrack2$ wget https://artifacts.picoctf.net/c/15/level2.py -- https://artifacts.picoctf.net/c/15/level2.flag.txt.enc
--2024-03-03 21:59:53--  https://artifacts.picoctf.net/c/15/level2.py
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 3.160.22.92, 3.160.22.128, 3.160.22.16, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|3.160.22.92|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 914 [application/octet-stream]
Saving to: 'level2.py'

level2.py                                                100%[=================================================================================================================================>]     914  --.-KB/s    in 0s      

2024-03-03 21:59:54 (342 MB/s) - 'level2.py' saved [914/914]

--2024-03-03 21:59:54--  https://artifacts.picoctf.net/c/15/level2.flag.txt.enc
Reusing existing connection to artifacts.picoctf.net:443.
HTTP request sent, awaiting response... 200 OK
Length: 31 [application/octet-stream]
Saving to: 'level2.flag.txt.enc'

level2.flag.txt.enc                                      100%[=================================================================================================================================>]      31  --.-KB/s    in 0s      

2024-03-03 21:59:54 (14.0 MB/s) - 'level2.flag.txt.enc' saved [31/31]

FINISHED --2024-03-03 21:59:54--
Total wall clock time: 0.1s
Downloaded: 2 files, 945 in 0s (194 MB/s)
arcf99-picoctf@webshell:~/pwCrack2$ ls
level2.flag.txt.enc  level2.py
arcf99-picoctf@webshell:~/pwCrack2$ python level2.py 
Please enter correct password for flag: 123
That password is incorrect
arcf99-picoctf@webshell:~/pwCrack2$ nano level2.py 
arcf99-picoctf@webshell:~/pwCrack2$ python 
Python 3.10.6 (main, Aug 10 2022, 11:40:04) [GCC 11.3.0] on linux
Type "help", "copyright", "credits" or "license" for more information.
>>> flag_part = chr(0x33) + chr(0x39) + chr(0x63) + chr(0x65)
>>> flag_part
'39ce'
>>> exit()
arcf99-picoctf@webshell:~/pwCrack2$ python level2.py 
Please enter correct password for flag: 39ce
Welcome back... your flag, user:
picoCTF{tr45h_51ng1ng_502ec42e}
arcf99-picoctf@webshell:~/pwCrack2$ 
```

## Notas adicionales

## Referencias