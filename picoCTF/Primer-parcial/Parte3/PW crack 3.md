## Objetivo
Can you crack the password to get the flag?Download the password checker [here](https://artifacts.picoctf.net/c/16/level3.py) and you'll need the encrypted [flag](https://artifacts.picoctf.net/c/16/level3.flag.txt.enc) and the [hash](https://artifacts.picoctf.net/c/16/level3.hash.bin) in the same directory too.There are 7 potential passwords with 1 being correct. You can find these by examining the password checker script.

## Pistas
1. To view the level3.hash.bin file in the webshell, do: `$ bvi level3.hash.bin`
2. To exit `bvi` type `:q` and press enter.
3. The `str_xor` function does not need to be reverse engineered for this challenge.
## Solución
Dentro del codigo del nivel, nos encontramos con lo siguiente:
The strings below are 7 possibilities for the correct password.  (Only 1 is correct)
pos_pw_list = ["6997", "3ac8", "f0ac", "4b17", "ec27", "4e66", "865e"]

Probando cada una de las contraseñas obtenemos que "865e" es la correcta y nos da la bandera picoCTF{m45h_fl1ng1ng_2b072a90}
```
arcf99-picoctf@webshell:~$ mkdir pwCrack3
arcf99-picoctf@webshell:~$ cd pwCrack3
arcf99-picoctf@webshell:~/pwCrack3$ wget https://artifacts.picoctf.net/c/16/level3.py -- https://artifacts.picoctf.net/c/16/level3.flag.txt.enc -- https://artifacts.picoctf.net/c/16/level3.hash.bin
--2024-03-03 22:07:05--  https://artifacts.picoctf.net/c/16/level3.py
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 3.160.22.16, 3.160.22.43, 3.160.22.128, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|3.160.22.16|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 1337 (1.3K) [application/octet-stream]
Saving to: 'level3.py'

level3.py                                                100%[=================================================================================================================================>]   1.31K  --.-KB/s    in 0s      

2024-03-03 22:07:05 (48.8 MB/s) - 'level3.py' saved [1337/1337]

--2024-03-03 22:07:05--  https://artifacts.picoctf.net/c/16/level3.flag.txt.enc
Reusing existing connection to artifacts.picoctf.net:443.
HTTP request sent, awaiting response... 200 OK
Length: 31 [application/octet-stream]
Saving to: 'level3.flag.txt.enc'

level3.flag.txt.enc                                      100%[=================================================================================================================================>]      31  --.-KB/s    in 0s      

2024-03-03 22:07:05 (179 KB/s) - 'level3.flag.txt.enc' saved [31/31]

--2024-03-03 22:07:05--  http://--/
Resolving -- (--)... failed: Name or service not known.
wget: unable to resolve host address '--'
--2024-03-03 22:07:05--  https://artifacts.picoctf.net/c/16/level3.hash.bin
Reusing existing connection to artifacts.picoctf.net:443.
HTTP request sent, awaiting response... 200 OK
Length: 16 [application/octet-stream]
Saving to: 'level3.hash.bin'

level3.hash.bin                                          100%[=================================================================================================================================>]      16  --.-KB/s    in 0s      

2024-03-03 22:07:05 (366 KB/s) - 'level3.hash.bin' saved [16/16]

FINISHED --2024-03-03 22:07:05--
Total wall clock time: 0.2s
Downloaded: 3 files, 1.4K in 0s (5.54 MB/s)
arcf99-picoctf@webshell:~/pwCrack3$ ls   
level3.flag.txt.enc  level3.hash.bin  level3.py
arcf99-picoctf@webshell:~/pwCrack3$ nano level3.py 
arcf99-picoctf@webshell:~/pwCrack3$ python level3.py 
Please enter correct password for flag: 6997
That password is incorrect
arcf99-picoctf@webshell:~/pwCrack3$ python level3.py 
Please enter correct password for flag: 3ac8
That password is incorrect
arcf99-picoctf@webshell:~/pwCrack3$ python level3.py 
Please enter correct password for flag: f0ac
That password is incorrect
arcf99-picoctf@webshell:~/pwCrack3$ python level3.py 
Please enter correct password for flag: 4b17
That password is incorrect
arcf99-picoctf@webshell:~/pwCrack3$ python level3.py 
Please enter correct password for flag: ec27
That password is incorrect
arcf99-picoctf@webshell:~/pwCrack3$ python level3.py 
Please enter correct password for flag: 4e66
That password is incorrect
arcf99-picoctf@webshell:~/pwCrack3$ python level3.py 
Please enter correct password for flag: 865e
Welcome back... your flag, user:
picoCTF{m45h_fl1ng1ng_2b072a90}
arcf99-picoctf@webshell:~/pwCrack3$ 
```
## Notas adicionales

## Referencias