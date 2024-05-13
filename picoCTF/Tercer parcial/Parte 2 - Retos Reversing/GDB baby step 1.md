## Objetivo
Can you figure out what is in the `eax` register at the end of the `main` function? Put your answer in the picoCTF flag format: `picoCTF{n}` where `n` is the contents of the `eax` register in the decimal number base. If the answer was `0x11` your flag would be `picoCTF{17}`.Disassemble [this](https://artifacts.picoctf.net/c/512/debugger0_a).

## Pistas
1. gdb is a very good debugger to use for this problem and many others!
2. `main` is actually a recognized symbol that can be used with gdb commands.

## Solución

```
arcf99-picoctf@webshell:~/tercerParial/gdb1$ wget https://artifacts.picoctf.net/c/512/debugger0_a
--2024-05-13 01:36:17--  https://artifacts.picoctf.net/c/512/debugger0_a
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 3.160.22.128, 3.160.22.43, 3.160.22.92, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|3.160.22.128|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 16472 (16K) [application/octet-stream]
Saving to: 'debugger0_a'

debugger0_a                                              100%[=================================================================================================================================>]  16.09K  --.-KB/s    in 0s      

2024-05-13 01:36:17 (40.1 MB/s) - 'debugger0_a' saved [16472/16472]

arcf99-picoctf@webshell:~/tercerParial/gdb1$ ls
debugger0_a
arcf99-picoctf@webshell:~/tercerParial/gdb1$ file debugger0_a 
debugger0_a: ELF 64-bit LSB pie executable, x86-64, version 1 (SYSV), dynamically linked, interpreter /lib64/ld-linux-x86-64.so.2, BuildID[sha1]=15a10290db2cd2ec0c123cf80b88ed7d7f5cf9ff, for GNU/Linux 3.2.0, not stripped
arcf99-picoctf@webshell:~/tercerParial/gdb1$ gdb debug
debug    debugfs  
arcf99-picoctf@webshell:~/tercerParial/gdb1$ gdb debug
debug    debugfs  
arcf99-picoctf@webshell:~/tercerParial/gdb1$ gdb debugger0_a
GNU gdb (Ubuntu 12.1-0ubuntu1~22.04) 12.1
Copyright (C) 2022 Free Software Foundation, Inc.
License GPLv3+: GNU GPL version 3 or later <http://gnu.org/licenses/gpl.html>
This is free software: you are free to change and redistribute it.
There is NO WARRANTY, to the extent permitted by law.
Type "show copying" and "show warranty" for details.
This GDB was configured as "x86_64-linux-gnu".
Type "show configuration" for configuration details.
For bug reporting instructions, please see:
<https://www.gnu.org/software/gdb/bugs/>.
Find the GDB manual and other documentation resources online at:
    <http://www.gnu.org/software/gdb/documentation/>.

For help, type "help".
Type "apropos word" to search for commands related to "word"...
Reading symbols from debugger0_a...
(No debugging symbols found in debugger0_a)
(gdb) info function
All defined functions:

Non-debugging symbols:
0x0000000000001000  _init
0x0000000000001030  __cxa_finalize@plt
0x0000000000001040  _start
0x0000000000001070  deregister_tm_clones
0x00000000000010a0  register_tm_clones
0x00000000000010e0  __do_global_dtors_aux
0x0000000000001120  frame_dummy
0x0000000000001129  main
0x0000000000001140  __libc_csu_init
0x00000000000011b0  __libc_csu_fini
0x00000000000011b8  _fini
(gdb) disas main
Dump of assembler code for function main:
   0x0000000000001129 <+0>:     endbr64 
   0x000000000000112d <+4>:     push   %rbp
   0x000000000000112e <+5>:     mov    %rsp,%rbp
   0x0000000000001131 <+8>:     mov    %edi,-0x4(%rbp)
   0x0000000000001134 <+11>:    mov    %rsi,-0x10(%rbp)
   0x0000000000001138 <+15>:    mov    $0x86342,%eax
   0x000000000000113d <+20>:    pop    %rbp
   0x000000000000113e <+21>:    ret    
End of assembler dump.
(gdb) q
arcf99-picoctf@webshell:~/tercerParial/gdb1$ python
Python 3.10.12 (main, Nov 20 2023, 15:14:05) [GCC 11.4.0] on linux
Type "help", "copyright", "credits" or "license" for more information.
>>> 0x86342
549698
>>> 
KeyboardInterrupt
>>> exit()
arcf99-picoctf@webshell:~/tercerParial/gdb1$ 
```

Lo ponemos en el formato que corresponde y obtenemos que la bandera es picoCTF{549698}
## Notas adicionales

## Referencias
[GDB baby step 1 - HackMD](https://hackmd.io/@nataliepjlin/rkObGE8oh)



