## Objetivo
Fix the syntax error in this Python script to print the flag.[Download Python script](https://artifacts.picoctf.net/c/27/fixme1.py)
## Pistas
1. Indentation is very meaningful in Python
2. To view the file in the webshell, do: `$ nano fixme1.py`
3. To exit `nano`, press Ctrl and x and follow the on-screen prompts.
4. The `str_xor` function does not need to be reverse engineered for this challenge.

## Solución
La solución implica descargar un script de Python (`fixme1.py`) desde una URL específica, y luego intentar ejecutar el script. Al ejecutarlo inicialmente, se encuentra con un error de indentación en el código. Después de editar el archivo `fixme1.py` para corregir el error de indentación que esta en el 'print', al volver a ejecutar el script se muestra correctamente la flag


```
arcf99-picoctf@webshell:~$ mkdir fixme1
arcf99-picoctf@webshell:~$ cd fixme1/
arcf99-picoctf@webshell:~/fixme1$ wget https://artifacts.picoctf.net/c/27/fixme1.py
--2024-03-03 21:16:34--  https://artifacts.picoctf.net/c/27/fixme1.py
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 3.160.22.92, 3.160.22.43, 3.160.22.16, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|3.160.22.92|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 837 [application/octet-stream]
Saving to: 'fixme1.py'

fixme1.py                                                100%[=================================================================================================================================>]     837  --.-KB/s    in 0s      

2024-03-03 21:16:34 (34.9 MB/s) - 'fixme1.py' saved [837/837]

arcf99-picoctf@webshell:~/fixme1$ ls
fixme1.py
arcf99-picoctf@webshell:~/fixme1$ python fixme1.py 
  File "/home/arcf99-picoctf/fixme1/fixme1.py", line 20
    print('That is correct! Here\'s your flag: ' + flag)
IndentationError: unexpected indent
arcf99-picoctf@webshell:~/fixme1$ nano fixme1.py 
arcf99-picoctf@webshell:~/fixme1$ nano fixme1.py 
arcf99-picoctf@webshell:~/fixme1$ python fixme1.py 
That is correct! Here's your flag: picoCTF{1nd3nt1ty_cr1515_182342f7}
arcf99-picoctf@webshell:~/fixme1$ 
```

## Notas adicionales

## Referencias