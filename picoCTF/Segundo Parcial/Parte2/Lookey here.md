## Objetivo
Attackers have hidden information in a very large mass of data in the past, maybe they are still doing it.Download the data [here](https://artifacts.picoctf.net/c/125/anthem.flag.txt).

## Pistas
1. Download the file and search for the flag based on the known prefix.

## Solución
```
┌──(kali㉿kali)-[~/Documents/retosForensic/segundoParcial/parte2]
└─$ mkdir lookey                                             
                                                                                                                   
┌──(kali㉿kali)-[~/Documents/retosForensic/segundoParcial/parte2]
└─$ cd lookey 
                                                                                                                   
┌──(kali㉿kali)-[~/…/retosForensic/segundoParcial/parte2/lookey]
└─$ wget https://artifacts.picoctf.net/c/125/anthem.flag.txt 
--2024-04-03 00:20:56--  https://artifacts.picoctf.net/c/125/anthem.flag.txt
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 3.161.55.64, 3.161.55.61, 3.161.55.26, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|3.161.55.64|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 108668 (106K) [application/octet-stream]
Saving to: ‘anthem.flag.txt’

anthem.flag.txt              100%[=============================================>] 106.12K  --.-KB/s    in 0.1s    

2024-04-03 00:20:57 (992 KB/s) - ‘anthem.flag.txt’ saved [108668/108668]

                                                                                                                   
┌──(kali㉿kali)-[~/…/retosForensic/segundoParcial/parte2/lookey]
└─$ ls
anthem.flag.txt
                                                                                                                   
┌──(kali㉿kali)-[~/…/retosForensic/segundoParcial/parte2/lookey]
└─$ grep "picoCTF{.*}" anthem.flag.txt
      we think that the men of picoCTF{gr3p_15_@w3s0m3_58f5c024}
                                                                                                                   
┌──(kali㉿kali)-[~/…/retosForensic/segundoParcial/parte2/lookey]
└─$ 

```
La etiqueta de la pregunta es grep, lo que indica que la pregunta está relacionada con grep, que es un comando para buscar patrones de texto y cadenas dentro de un archivo.

Sabiendo que la bandera tiene el formato picoCTF{texto}, podemos usar grep para buscar dichos patrones en el archivo de texto.

Ahora podemos ejecutar el siguiente comando en la terminal: grep "picoCTF{.*}" anthem.flag.txt, donde .* indica una cadena de cero o más instancias de cualquier carácter.

Esto nos da la bandera
## Notas adicionales

## Referencias



