## Objetivo
Matryoshka dolls are a set of wooden dolls of decreasing size placed one inside another. What's the final one? Image: [this](https://mercury.picoctf.net/static/f6cc2560a70b1ea811c151accba5390f/dolls.jpg)

## Pistas
1. Wait, you can hide files inside files? But how do you find them?
2. Make sure to submit the flag as picoCTF{XXXXX}

## Solución
Usamos el comando:
binwalk -e ... 

que que nos permite automatizar el proceso de extraer el sistema de archivos de un binario de un firmware hasta llegar a un archivo txt en el que esta nuestra bandera, sustituimos algunos caracteres con vi :

## Notas adicionales

## Referencias
https://www.youtube.com/watch?v=l2vvrJ3rB2A&t=150s



