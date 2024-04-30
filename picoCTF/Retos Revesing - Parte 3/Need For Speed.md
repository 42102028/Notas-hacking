## Objetivo
The name of the game is [speed](https://www.youtube.com/watch?v=8piqd2BWeGI). Are you quick enough to solve this problem and keep it above 50 mph? [need-for-speed](https://jupiter.challenges.picoctf.org/static/f9abc386dfb1309e687344783f208b20/need-for-speed).

## Pistas
1. What is the final key?

## Solución
PICOCTF{Good job keeping bus #190ca38b speeding along!}

En el desafío "needForSpeed", inicialmente intentas ejecutar un binario llamado need-for-speed, que falla con un "No es lo suficientemente rápido. ¡BOOM!" mensaje, probablemente debido a un cronómetro o control de velocidad. Usando GDB (GNU Debugger), lo configura para ignorar la señal SIGALRM, que probablemente se usa para activar el mensaje "¡BOOM!" evento si una condición no se cumple lo suficientemente rápido. Al ignorar esta señal, permite que el programa complete su ejecución y revele la bandera oculta sin interrupción. 
```
                                                                                                                    
┌──(kali㉿kali)-[~/Documents/retosPico/retosRevesring3/needForSpeed]
└─$ wget https://www.youtube.com/watch?v=8piqd2BWeGI                                            
--2024-04-30 19:46:31--  https://www.youtube.com/watch?v=8piqd2BWeGI
Resolving www.youtube.com (www.youtube.com)... 192.178.56.78, 142.251.218.142, 142.250.177.14, ...
Connecting to www.youtube.com (www.youtube.com)|192.178.56.78|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: unspecified [text/html]
Saving to: ‘watch?v=8piqd2BWeGI’

watch?v=8piqd2BWeGI              [    <=>                                        ] 922.87K   864KB/s    in 1.1s    

2024-04-30 19:46:32 (864 KB/s) - ‘watch?v=8piqd2BWeGI’ saved [945020]

                                                                                                                    
┌──(kali㉿kali)-[~/Documents/retosPico/retosRevesring3/needForSpeed]
└─$ wget https://jupiter.challenges.picoctf.org/static/f9abc386dfb1309e687344783f208b20/need-for-speed
--2024-04-30 19:46:39--  https://jupiter.challenges.picoctf.org/static/f9abc386dfb1309e687344783f208b20/need-for-speed
Resolving jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)... 3.131.60.8
Connecting to jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)|3.131.60.8|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 8888 (8.7K) [application/octet-stream]
Saving to: ‘need-for-speed’

need-for-speed               100%[==============================================>]   8.68K  --.-KB/s    in 0s      

2024-04-30 19:46:39 (311 MB/s) - ‘need-for-speed’ saved [8888/8888]

                                                                                                                    
┌──(kali㉿kali)-[~/Documents/retosPico/retosRevesring3/needForSpeed]
└─$ ls
 need-for-speed  'watch?v=8piqd2BWeGI'
                                                                                                                    
┌──(kali㉿kali)-[~/Documents/retosPico/retosRevesring3/needForSpeed]
└─$ chmod +x need-for-speed && ./need-for-speed        
Keep this thing over 50 mph!
============================

Creating key...
Not fast enough. BOOM!
                                                                                                                    
┌──(kali㉿kali)-[~/Documents/retosPico/retosRevesring3/needForSpeed]
└─$ gdb ./need-for-speed 
GNU gdb (Debian 13.2-1) 13.2
Copyright (C) 2023 Free Software Foundation, Inc.
License GPLv3+: GNU GPL version 3 or later <http://gnu.org/licenses/gpl.html>
This is free software: you are free to change and redistribute it.
There is NO WARRANTY, to the extent permitted by law.
Type "show copying" and "show warranty" for details.
This GDB was configured as "x86_64-linux-gnu".
Type "show configuration" for configuration details.
For bug reporting instructions, please see:
<https://www.gnu.org/software/gdb/bugs/>.
Find the GDB manual and other documentation resources online at:
    <http://www.gnu.org/software/gdb/documentation/>.

For help, type "help".
Type "apropos word" to search for commands related to "word"...
Reading symbols from ./need-for-speed...
(No debugging symbols found in ./need-for-speed)
(gdb) r
Starting program: /home/kali/Documents/retosPico/retosRevesring3/needForSpeed/need-for-speed 
[Thread debugging using libthread_db enabled]
Using host libthread_db library "/lib/x86_64-linux-gnu/libthread_db.so.1".
Keep this thing over 50 mph!
============================

Creating key...
Not fast enough. BOOM!
[Inferior 1 (process 15944) exited normally]
(gdb) handle SIGALRM ignore
Signal        Stop      Print   Pass to program Description
SIGALRM       No        No      No              Alarm clock
(gdb) r
Starting program: /home/kali/Documents/retosPico/retosRevesring3/needForSpeed/need-for-speed 
[Thread debugging using libthread_db enabled]
Using host libthread_db library "/lib/x86_64-linux-gnu/libthread_db.so.1".
Keep this thing over 50 mph!
============================

Creating key...
Finished
Printing flag:
PICOCTF{Good job keeping bus #190ca38b speeding along!}
[Inferior 1 (process 16251) exited normally]
(gdb) 

```
## Notas adicionales

## Referencias

https://github.com/HHousen/PicoCTF-2019/blob/master/Reverse%20Engineering/Need%20For%20Speed/README.md

