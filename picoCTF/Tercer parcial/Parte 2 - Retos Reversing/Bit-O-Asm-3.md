## Objetivo
Can you figure out what is in the `eax` register? Put your answer in the picoCTF flag format: `picoCTF{n}` where `n` is the contents of the `eax` register in the decimal number base. If the answer was `0x11` your flag would be `picoCTF{17}`.Download the assembly dump [here](https://artifacts.picoctf.net/c/530/disassembler-dump0_c.txt).

## Pistas
1. Not everything in this disassembly listing is optimal.
## Solución
picoCTF{2619997}

```
arcf99-picoctf@webshell:~/tercerParial/asm3$ python
Python 3.10.12 (main, Nov 20 2023, 15:14:05) [GCC 11.4.0] on linux
Type "help", "copyright", "credits" or "license" for more information.
>>> (0x9fe1a * 0x4) + 0x1f5
2619997
>>> 
```

## Notas adicionales

## Referencias
[Bit-O-Asm-3 - HackMD](https://hackmd.io/@nataliepjlin/rk8WYsNi2)



