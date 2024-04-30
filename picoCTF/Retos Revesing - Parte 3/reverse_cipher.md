## Objetivo
We have recovered a [binary](https://jupiter.challenges.picoctf.org/static/48babf8f8c4c6b8baf336680ea5b9ddf/rev) and a [text file](https://jupiter.challenges.picoctf.org/static/48babf8f8c4c6b8baf336680ea5b9ddf/rev_this). Can you reverse the flag.

## Pistas
1. objdump and Gihdra are some tools that could assist with this

## Solución
picoCTF{r3v3rs312528e05}


El archivo rev_this contiene una versión codificada de una bandera. Luego se utiliza una secuencia de comandos Python para decodificar esta bandera. El script lee el contenido de rev_this byte a byte, aplicando transformaciones específicas a cada byte dependiendo de su posición: para los primeros 8 bytes, los lee directamente; para los siguientes bytes, alterna entre restar 5 y sumar 2 según si el índice es par o impar; el byte final se lee directamente. Esto da como resultado que se reconstruya y muestre la bandera correcta.

```
                               
┌──(kali㉿kali)-[~/Documents/retosPico/retosRevesring3/reverseChiper]
└─$ ls                  
rev  rev_this
                                                                                                                    
┌──(kali㉿kali)-[~/Documents/retosPico/retosRevesring3/reverseChiper]
└─$ cat rev_this        
picoCTF{w1{1wq8/7376j.:}                                                                                                                    
┌──(kali㉿kali)-[~/Documents/retosPico/retosRevesring3/reverseChiper]
└─$ python
Python 3.11.8 (main, Feb  7 2024, 21:52:08) [GCC 13.2.0] on linux
Type "help", "copyright", "credits" or "license" for more information.
>>> # See forensics challenge "Investigative Reversing 2" for more info on the below script.
>>> # The challenges are similar.
>>> 
>>> flag = ""
>>> 
>>> with open("rev_this", "rb") as data:
...     for i in range(8):
...         flag += chr(data.read(1)[0])
...     for i in range(8, 23):
...         if (i & 1) == 0:
...             flag += chr(data.read(1)[0] - 5)
...         else:
...             flag += chr(data.read(1)[0] + 2)
...     flag+= chr(data.read(1)[0])
... 
>>> print("Flag: {}".format(flag))
Flag: picoCTF{r3v3rs312528e05}
>>> exit()
                                                                                                                    
┌──(kali㉿kali)-[~/Documents/retosPico/retosRevesring3/reverseChiper]
└─$ 

```


## Notas adicionales

## Referencias
https://picoctf2019.haydenhousen.com/reverse-engineering/reverse_cipher



