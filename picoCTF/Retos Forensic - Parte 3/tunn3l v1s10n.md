## Objetivo
We found this [file](https://mercury.picoctf.net/static/06a5e4ab22ba52cd66a038d51a6cc07b/tunn3l_v1s10n). Recover the flag.

## Pistas
1. Weird that it won't display right...

## Solución
```
┌──(kali㉿kali)-[~/Documents/retosForensic]
└─$ mkdir tunnel
                                                                                                                                                                                                                                           
┌──(kali㉿kali)-[~/Documents/retosForensic]
└─$ cd tunnel 
                                                                                                                                                                                                                                           
┌──(kali㉿kali)-[~/Documents/retosForensic/tunnel]
└─$ wget https://mercury.picoctf.net/static/06a5e4ab22ba52cd66a038d51a6cc07b/tunn3l_v1s10n
--2024-03-23 20:30:33--  https://mercury.picoctf.net/static/06a5e4ab22ba52cd66a038d51a6cc07b/tunn3l_v1s10n
Resolving mercury.picoctf.net (mercury.picoctf.net)... 18.189.209.142
Connecting to mercury.picoctf.net (mercury.picoctf.net)|18.189.209.142|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 2893454 (2.8M) [application/octet-stream]
Saving to: ‘tunn3l_v1s10n’

tunn3l_v1s10n                                              100%[=======================================================================================================================================>]   2.76M   711KB/s    in 4.5s    

2024-03-23 20:30:38 (631 KB/s) - ‘tunn3l_v1s10n’ saved [2893454/2893454]

                                                                                                                                                                                                                                           
┌──(kali㉿kali)-[~/Documents/retosForensic/tunnel]
└─$ ls
tunn3l_v1s10n
                                                                                                                                                                                                                                           
┌──(kali㉿kali)-[~/Documents/retosForensic/tunnel]
└─$ file tunn3l_v1s10n 
tunn3l_v1s10n: data
                                                                                                                                                                                                                                           
┌──(kali㉿kali)-[~/Documents/retosForensic/tunnel]
└─$ xxd -g 1 tunn3l_v1s10n | head
00000000: 42 4d 8e 26 2c 00 00 00 00 00 ba d0 00 00 ba d0  BM.&,...........
00000010: 00 00 6e 04 00 00 32 01 00 00 01 00 18 00 00 00  ..n...2.........
00000020: 00 00 58 26 2c 00 25 16 00 00 25 16 00 00 00 00  ..X&,.%...%.....
00000030: 00 00 00 00 00 00 23 1a 17 27 1e 1b 29 20 1d 2a  ......#..'..) .*
00000040: 21 1e 26 1d 1a 31 28 25 35 2c 29 33 2a 27 38 2f  !.&..1(%5,)3*'8/
00000050: 2c 2f 26 23 33 2a 26 2d 24 20 3b 32 2e 32 29 25  ,/&#3*&-$ ;2.2)%
00000060: 30 27 23 33 2a 26 38 2c 28 36 2b 27 39 2d 2b 2f  0'#3*&8,(6+'9-+/
00000070: 26 23 1d 12 0e 23 17 11 29 16 0e 55 3d 31 97 76  &#...#..)..U=1.v
00000080: 66 8b 66 52 99 6d 56 9e 70 58 9e 6f 54 9c 6f 54  f.fR.mV.pX.oT.oT
00000090: ab 7e 63 ba 8c 6d bd 8a 69 c8 97 71 c1 93 71 c1  .~c..m..i..q..q.
                                                             
┌──(kali㉿kali)-[~/Documents/retosForensic/tunnel]
└─$ hexeditor tunn3l_v1s10n 

zsh: suspended  hexeditor tunn3l_v1s10n
                                                             
┌──(kali㉿kali)-[~/Documents/retosForensic/tunnel]
└─$ hexeditor tunn3l_v1s10n
                                                                    
┌──(kali㉿kali)-[~/Documents/retosForensic/tunnel]
└─$ open tunn3l_v1s10n           
                                                                    
┌──(kali㉿kali)-[~/Documents/retosForensic/tunnel]
└─$ hexeditor tunn3l_v1s10n
                                                               
┌──(kali㉿kali)-[~/Documents/retosForensic/tunnel]
└─$ open tunn3l_v1s10n 
```

Abrimos la imagen en photopea ya que pude leer archivos .BMP y en la imagen podemos ver la bandera 
## Notas adicionales

## Referencias
https://www.photopea.com/?p=%7B%22files%22:%5B%22data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAAAUAAAAFCAYAAACNbyblAAAAHElEQVQI12P4//8/w38GIAXDIBKE0DHxgljNBAAO9TXL0Y4OHwAAAABJRU5ErkJggg==%22%5D%7D
https://medium.com/@MonlesYen/pico-ctf-writeup-within-forensics-03-tunn3l-v1s10n-glory-of-the-garden-cfe3a6271991



