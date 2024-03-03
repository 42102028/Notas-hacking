## Objetivo
To get truly 1337, you must understand different data encodings, such as hexadecimal or binary. Can you get the flag from this program to prove you are on the way to becoming 1337? Connect with `nc jupiter.challenges.picoctf.org 29956`.

## Pistas
1. I hear python can convert things.
2. It might help to have multiple windows open.

## Solución
Este desafío de implica conectarse a un servidor a través de netcat (`nc`) y recibir varios tipos de desafíos que requieren convertir datos de una forma a otra dentro de un límite de tiempo de 45 segundos por pregunta. 
Aquí se presentan tres tipos de conversiones:

1. **Binario a Texto**: Se pide convertir una secuencia de números binarios  a texto. 
    
2. **Octal a Texto**: Luego, se solicita convertir una serie de números en base octal
    
3. **Hexadecimal a Texto**: Finalmente, se pide convertir una cadena hexadecimal a texto.
    

Respondiendo correctamente a cada pregunta dentro del límite de tiempo, se supera el desafío y se revela la flag:

```
arcf99-picoctf@webshell:~$ nc jupiter.challenges.picoctf.org 29956
Let us see how data is stored
table
Please give the 01110100 01100001 01100010 01101100 01100101 as a word.
...
you have 45 seconds.....

Input:
table
Please give me the  146 141 154 143 157 156 as a word.
Input:
falcon
Please give me the 70656172 as a word.
Input:
pear
You've beaten the challenge
Flag: picoCTF{learning_about_converting_values_b375bb16}
```

## Notas adicionales

## Referencias
[Conversor de código binario a ASCII (calculadoraconversor.com)](https://www.calculadoraconversor.com/binario-a-ascii/)
[Convert Octal to ASCII – Online ASCII Tools (onlinetools.com)](https://onlinetools.com/ascii/convert-octal-to-ascii)
[Conversión Hexadecimal a Ascii (chileoffshore.com)](https://www.chileoffshore.com/es/toolkits/basic-conversion/hexa-to-ascii)