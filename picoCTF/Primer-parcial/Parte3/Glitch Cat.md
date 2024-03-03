## Objetivo
Our flag printing service has started glitching!`$ nc saturn.picoctf.net 52682`

## Pistas
1. ASCII is one of the most common encodings used in programming
2. We know that the glitch output is valid Python, somehow!
3. Press Ctrl and c on your keyboard to close your connection and return to the command prompt.

## Solución
La solución comienza con una conexión a un servicio en `saturn.picoctf.net` en el puerto `52682` usando `nc` (netcat), que proporciona una parte de la flag en forma de una expresión de Python. 
Esta expresión incluye una combinación de texto plano y llamadas a la función `chr()` con valores hexadecimales como argumentos, que cuando se ejecutan en Python, convierten los valores hexadecimales en caracteres ASCII.

Para obtener la flag completa, se copia esta expresión a una sesión de Python y se ejecuta. La función `chr()` convierte cada valor hexadecimal en su correspondiente carácter ASCII, formando así la parte faltante de la flag. Al concatenar estos caracteres al texto dado, se revela la flag completa

```
arcf99-picoctf@webshell:~$ nc saturn.picoctf.net 52682
'picoCTF{gl17ch_m3_n07_' + chr(0x62) + chr(0x64) + chr(0x61) + chr(0x36) + chr(0x38) + chr(0x66) + chr(0x37) + chr(0x35) + '}'
^C
arcf99-picoctf@webshell:~$ python
Python 3.10.6 (main, Aug 10 2022, 11:40:04) [GCC 11.3.0] on linux
Type "help", "copyright", "credits" or "license" for more information.
>>> flag_part = 'picoCTF{gl17ch_m3_n07_' + chr(0x62) + chr(0x64) + chr(0x61) + chr(0x36) + chr(0x38) + chr(0x66) + chr(0x37) + chr(0x35) + '}'
>>> flag_part
'picoCTF{gl17ch_m3_n07_bda68f75}'
>>> 
```

## Notas adicionales
La función `chr()` en Python toma un entero que representa un punto de código Unicode y devuelve el carácter correspondiente a ese punto de código. Esencialmente, convierte un número (en este caso, un valor en hexadecimal representado como un entero) en el carácter que representa en la codificación Unicode. Por ejemplo, `chr(0x62)` convierte el valor hexadecimal `0x62` (que es `98` en decimal) al carácter ASCII 'b'. Esta función es útil para trabajar con caracteres individuales y realizar conversiones entre representaciones numéricas y su correspondiente carácter imprimible.

## Referencias