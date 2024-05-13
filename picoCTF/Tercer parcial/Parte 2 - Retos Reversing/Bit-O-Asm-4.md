## Objetivo
Can you figure out what is in the `eax` register? Put your answer in the picoCTF flag format: `picoCTF{n}` where `n` is the contents of the `eax` register in the decimal number base. If the answer was `0x11` your flag would be `picoCTF{17}`.Download the assembly dump [here](https://artifacts.picoctf.net/c/511/disassembler-dump0_d.txt).

## Pistas
1. Don't tell anyone I told you this, but you can solve this problem without understanding the compare/jump relationship.
2. Of course, if you're really good, you'll only need one attempt to solve this problem.
## Solución
picoCTF{654773}
```
arcf99-picoctf@webshell:~/tercerParial/asm$ wget https://artifacts.picoctf.net/c/511/disassembler-dump0_d.txt
--2024-05-13 01:34:17--  https://artifacts.picoctf.net/c/511/disassembler-dump0_d.txt
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 3.160.22.92, 3.160.22.16, 3.160.22.43, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|3.160.22.92|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 482 [application/octet-stream]
Saving to: 'disassembler-dump0_d.txt'

disassembler-dump0_d.txt                                 100%[=================================================================================================================================>]     482  --.-KB/s    in 0s      

2024-05-13 01:34:17 (246 MB/s) - 'disassembler-dump0_d.txt' saved [482/482]

arcf99-picoctf@webshell:~/tercerParial/asm$ ls
disassembler-dump0_d.txt
arcf99-picoctf@webshell:~/tercerParial/asm$ cat disassembler-dump0_d.txt 
<+0>:     endbr64 
<+4>:     push   rbp
<+5>:     mov    rbp,rsp
<+8>:     mov    DWORD PTR [rbp-0x14],edi
<+11>:    mov    QWORD PTR [rbp-0x20],rsi
<+15>:    mov    DWORD PTR [rbp-0x4],0x9fe1a
<+22>:    cmp    DWORD PTR [rbp-0x4],0x2710
<+29>:    jle    0x55555555514e <main+37>
<+31>:    sub    DWORD PTR [rbp-0x4],0x65
<+35>:    jmp    0x555555555152 <main+41>
<+37>:    add    DWORD PTR [rbp-0x4],0x65
<+41>:    mov    eax,DWORD PTR [rbp-0x4]
<+44>:    pop    rbp
<+45>:    ret
arcf99-picoctf@webshell:~/tercerParial/asm$ python
Python 3.10.12 (main, Nov 20 2023, 15:14:05) [GCC 11.4.0] on linux
Type "help", "copyright", "credits" or "license" for more information.
>>> 0x9fe1a
654874
>>> exit()
arcf99-picoctf@webshell:~/tercerParial/asm$ 
```

## Notas adicionales

## Referencias
[Bit-O-Asm-4 - HackMD](https://hackmd.io/@nataliepjlin/S1jn0JBsn)



