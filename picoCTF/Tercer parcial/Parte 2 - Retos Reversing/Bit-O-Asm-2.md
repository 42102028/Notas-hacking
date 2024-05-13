## Objetivo
Can you figure out what is in the `eax` register? Put your answer in the picoCTF flag format: `picoCTF{n}` where `n` is the contents of the `eax` register in the decimal number base. If the answer was `0x11` your flag would be `picoCTF{17}`.Download the assembly dump [here](https://artifacts.picoctf.net/c/510/disassembler-dump0_b.txt).
## Pistas
1. `PTR`'s or 'pointers', reference a location in memory where values can be stored.
## Solución
PicoCTF{654874}

ignoramos la mayoría de las líneas iniciales hasta llegar a la línea <+15> cuando se pasa 0x9fe1a al registro de puntero base. En la línea <+22>, movemos este valor desde el puntero base en esta dirección a eax, y encontramos nuestro valor almacenado en eax. En este punto, convertimos 0x9fe1a a decimal y encontramos que representa el número 654874. Ahora, podemos ponerlo en la sintaxis de PicoCTF como PicoCTF{654874}

## Notas adicionales

## Referencias
[PicoCTF Bit-O-Asm 2 Reverse Engineering - HackMD](https://hackmd.io/@cmonast/ryJLkBtHa)


