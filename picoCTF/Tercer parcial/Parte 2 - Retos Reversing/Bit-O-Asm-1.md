## Objetivo
Can you figure out what is in the `eax` register? Put your answer in the picoCTF flag format: `picoCTF{n}` where `n` is the contents of the `eax` register in the decimal number base. If the answer was `0x11` your flag would be `picoCTF{17}`.Download the assembly dump [here](https://artifacts.picoctf.net/c/509/disassembler-dump0_a.txt).
## Pistas
1. As with most assembly, there is a lot of noise in the instruction dump. Find the one line that pertains to this question and don't second guess yourself!

## Solución
picoCTF{48}
```
arcf99-picoctf@webshell:~/tercerParial$ ls
ASCII  crackME  crackme.py  disassembler-dump0_a.txt  enc  key  script.py
arcf99-picoctf@webshell:~/tercerParial$ cat disassembler-dump0_a.txt 
<+0>:     endbr64 
<+4>:     push   rbp
<+5>:     mov    rbp,rsp
<+8>:     mov    DWORD PTR [rbp-0x4],edi
<+11>:    mov    QWORD PTR [rbp-0x10],rsi
<+15>:    mov    eax,0x30
<+20>:    pop    rbp
<+21>:    ret
arcf99-picoctf@webshell:~/tercerParial$ cat disassembler-dump0_a.txt | grep "eax"
<+15>:    mov    eax,0x30
arcf99-picoctf@webshell:~/tercerParial$ python
Python 3.10.12 (main, Nov 20 2023, 15:14:05) [GCC 11.4.0] on linux
Type "help", "copyright", "credits" or "license" for more information.
>>> print(int("0x30",16))
48
>>> exit()
```

## Notas adicionales

## Referencias
[Bit-O-Asm-1 - HackMD](https://hackmd.io/@nataliepjlin/S1d-dq4s3)



