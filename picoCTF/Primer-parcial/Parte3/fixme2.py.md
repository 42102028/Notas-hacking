## Objetivo
Fix the syntax error in the Python script to print the flag.[Download Python script](https://artifacts.picoctf.net/c/4/fixme2.py)

## Pistas
1. Are equality and assignment the same symbol?
2. To view the file in the webshell, do: `$ nano fixme2.py`
3. To exit `nano`, press Ctrl and x and follow the on-screen prompts.
4. The `str_xor` function does not need to be reverse engineered for this challenge.


## Solución

La solución involucra descargar un script de Python (`fixme2.py`) desde una URL específica, e intentar ejecutar el script. Inicialmente, la ejecución falla debido a un error de sintaxis, específicamente un error de asignación (`=`) donde debería haber una comparación (`==`). Tras editar el archivo `fixme2.py` para corregir este error, reemplazando `=` por `==` en la condición. La ejecución posterior del script muestra correctamente la flag
```
arcf99-picoctf@webshell:~$ mkdir fixMe2
arcf99-picoctf@webshell:~$ cd fixMe2/
arcf99-picoctf@webshell:~/fixMe2$ wget https://artifacts.picoctf.net/c/4/fixme2.py
--2024-03-03 21:32:49--  https://artifacts.picoctf.net/c/4/fixme2.py
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 3.160.22.128, 3.160.22.43, 3.160.22.16, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|3.160.22.128|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 1029 (1.0K) [application/octet-stream]
Saving to: 'fixme2.py'

fixme2.py                                                100%[=================================================================================================================================>]   1.00K  --.-KB/s    in 0s      

2024-03-03 21:32:50 (418 MB/s) - 'fixme2.py' saved [1029/1029]

arcf99-picoctf@webshell:~/fixMe2$ ls
fixme2.py
arcf99-picoctf@webshell:~/fixMe2$ python fixme2.py 
  File "/home/arcf99-picoctf/fixMe2/fixme2.py", line 22
    if flag = "":
       ^^^^^^^^^
SyntaxError: invalid syntax. Maybe you meant '==' or ':=' instead of '='?
arcf99-picoctf@webshell:~/fixMe2$ nano fixme2.py 
arcf99-picoctf@webshell:~/fixMe2$ python fixme2.py 
That is correct! Here's your flag: picoCTF{3qu4l1ty_n0t_4551gnm3nt_e8814d03}
```
## Notas adicionales

## Referencias