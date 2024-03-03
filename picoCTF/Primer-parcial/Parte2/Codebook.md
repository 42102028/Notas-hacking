## Objetivo
Run the Python script `code.py` in the same directory as `codebook.txt`.

- [Download code.py](https://artifacts.picoctf.net/c/3/code.py)
- [Download codebook.txt](https://artifacts.picoctf.net/c/3/codebook.txt)

## Pistas
On the webshell, use `ls` to see if both files are in the directory you are in

The `str_xor` function does not need to be reverse engineered for this challenge.

## Solución
  
La solución implica descargar dos archivos, `code.py` y `codebook.txt`, desde un servidor remoto a un directorio local llamado. Después de descargar los archivos, se ejecuta el script `code.py` con Python, lo cual genera la flag

```
arcf99-picoctf@webshell:~$ mkdir codebook
arcf99-picoctf@webshell:~$ cd codebook/
arcf99-picoctf@webshell:~/codebook$ wget https://artifacts.picoctf.net/c/3/code.py -- https://artifacts.picoctf.net/c/3/codebook.txt
--2024-03-03 21:03:12--  https://artifacts.picoctf.net/c/3/code.py
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 3.160.22.16, 3.160.22.128, 3.160.22.92, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|3.160.22.16|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 1278 (1.2K) [application/octet-stream]
Saving to: 'code.py'

code.py                                                  100%[=================================================================================================================================>]   1.25K  --.-KB/s    in 0s      

2024-03-03 21:03:12 (509 MB/s) - 'code.py' saved [1278/1278]

--2024-03-03 21:03:12--  https://artifacts.picoctf.net/c/3/codebook.txt
Reusing existing connection to artifacts.picoctf.net:443.
HTTP request sent, awaiting response... 200 OK
Length: 27 [application/octet-stream]
Saving to: 'codebook.txt'

codebook.txt                                             100%[=================================================================================================================================>]      27  --.-KB/s    in 0s      

2024-03-03 21:03:12 (6.92 MB/s) - 'codebook.txt' saved [27/27]

FINISHED --2024-03-03 21:03:12--
Total wall clock time: 0.1s
Downloaded: 2 files, 1.3K in 0s (203 MB/s)
arcf99-picoctf@webshell:~/codebook$ ls
code.py  codebook.txt
arcf99-picoctf@webshell:~/codebook$ python code.py
picoCTF{c0d3b00k_455157_197a982c}
```

## Notas adicionales

## Referencias