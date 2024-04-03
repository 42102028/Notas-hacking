## Objetivo
Files can always be changed in a secret way. Can you find the flag? [cat.jpg](https://mercury.picoctf.net/static/a614a27d4cb251d04c7d2f3f3f76a965/cat.jpg)

## Pistas
1. Look at the details of the file
2. Make sure to submit the flag as picoCTF{XXXXX}

## Solución
Primero, intenté usar binwalk para extraer archivos de la imagen, pero no pude encontrar nada. Luego decidí usar exiftool para verificar los metadatos de la imagen. Aquí, noté que la sección "Licencia" parecía tener un valor extraño, ¡así que decidí decodificarla en base64 usando cyberchef y viola! Conseguí la bandera para la cuerda.

picoCTF{the_m3tadata_1s_modified}

## Notas adicionales


## Referencias
https://solvenite.medium.com/information-picoctf-writeup-56878eef8c4a



