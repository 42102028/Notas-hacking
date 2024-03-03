## Objetivo
Can you crack the password to get the flag?Download the password checker [here](https://artifacts.picoctf.net/c/10/level1.py) and you'll need the encrypted [flag](https://artifacts.picoctf.net/c/10/level1.flag.txt.enc) in the same directory too.

## Pistas
1. To view the file in the webshell, do: `$ nano level1.py`
2. To exit `nano`, press Ctrl and x and follow the on-screen prompts.
3. The `str_xor` function does not need to be reverse engineered for this challenge.

## Solución
La solución involucra descargar un script de Python (`level1.py`) y un archivo cifrado (`level1.flag.txt.enc`) desde un servidor. 

Al intentar ejecutar `level1.py`, se solicita una contraseña para desbloquear la flag. Tras un intento fallido con una contraseña incorrecta, se edita `level1.py` en el que podemos ver que la funcion que nos da la bandera, tiene la cadena necesaria para que nos muestre la bandera y en un segundo intento con la contraseña correcta `691d`, el script revela la flag: `picoCTF{545h_r1ng1ng_56891419}`

![[Pasted image 20240303155804.png]]

```
arcf99-picoctf@webshell:~/pwCrack1$ wget https://artifacts.picoctf.net/c/10/level1.py -- https://artifacts.picoctf.net/c/10/level1.flag.txt.enc
--2024-03-03 21:50:06--  https://artifacts.picoctf.net/c/10/level1.py
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 3.160.22.16, 3.160.22.43, 3.160.22.128, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|3.160.22.16|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 876 [application/octet-stream]
Saving to: 'level1.py'

level1.py                                                100%[=================================================================================================================================>]     876  --.-KB/s    in 0s      

2024-03-03 21:50:06 (44.9 MB/s) - 'level1.py' saved [876/876]

--2024-03-03 21:50:06--  https://artifacts.picoctf.net/c/10/level1.flag.txt.enc
Reusing existing connection to artifacts.picoctf.net:443.
HTTP request sent, awaiting response... 200 OK
Length: 30 [application/octet-stream]
Saving to: 'level1.flag.txt.enc'

level1.flag.txt.enc                                      100%[=================================================================================================================================>]      30  --.-KB/s    in 0s      

2024-03-03 21:50:06 (532 KB/s) - 'level1.flag.txt.enc' saved [30/30]

FINISHED --2024-03-03 21:50:06--
Total wall clock time: 0.1s
Downloaded: 2 files, 906 in 0s (11.7 MB/s)
arcf99-picoctf@webshell:~/pwCrack1$ ls
level1.flag.txt.enc  level1.py
arcf99-picoctf@webshell:~/pwCrack1$ python level1.py 
Please enter correct password for flag: 123
That password is incorrect
arcf99-picoctf@webshell:~/pwCrack1$ nano level1.py
arcf99-picoctf@webshell:~/pwCrack1$ python level1.py 
Please enter correct password for flag: 691d
Welcome back... your flag, user:
picoCTF{545h_r1ng1ng_56891419}
arcf99-picoctf@webshell:~/pwCrack1$ 
```

## Notas adicionales

## Referencias