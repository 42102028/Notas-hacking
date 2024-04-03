## Objetivo
Download this image and find the flag.

- [Download image](https://artifacts.picoctf.net/c/216/pico.flag.png)

## Pistas
1. We know the end sequence of the message will be `$t3g0`.

## Solución
picoCTF{7h3r3_15_n0_5p00n_a1062667}
```
┌──(kali㉿kali)-[~/…/retosForensic/segundoParcial/parte2/stego]
└─$ zsteg pico.flag.png 
b1,rgb,lsb,xy       .. text: "picoCTF{7h3r3_15_n0_5p00n_a1062667}$t3g0"
b1,abgr,lsb,xy      .. text: "E2A5q4E%uSA"
b2,b,lsb,xy         .. text: "AAPAAQTAAA"
b2,b,msb,xy         .. text: "HWUUUUUU"
b3,r,lsb,xy         .. file: gfxboot compiled html help file
b4,r,lsb,xy         .. file: Targa image data (16-273) 65536 x 4097 x 1 +4352 +4369 - 1-bit alpha - right "\021\020\001\001\021\021\001\001\021\021\001"
b4,g,lsb,xy         .. file: 0420 Alliant virtual executable not stripped
b4,b,lsb,xy         .. file: Targa image data - Map 272 x 17 x 16 +257 +272 - 1-bit alpha "\020\001\021\001\021\020\020\001\020\001\020\001"
b4,bgr,lsb,xy       .. file: Targa image data - Map 273 x 272 x 16 +1 +4113 - 1-bit alpha "\020\001\001\001"
b4,rgba,msb,xy      .. file: Applesoft BASIC program data, first line number 8
                                                                                                                   
┌──(kali㉿kali)-[~/…/retosForensic/segundoParcial/parte2/stego]
└─$ 

```


## Notas adicionales

## Referencias
[stego picoCTF - Buscar con Google](https://www.google.com/search?sca_esv=b91db504c3362682&sxsrf=ACQVn0-QNFU1wopxAF8rojNeFaNjGMLLOg:1712120302035&q=stego++picoCTF&tbm=vid&source=lnms&prmd=sivnbmtz&sa=X&ved=2ahUKEwizlKmToaWFAxUv5MkDHW_LDU8Q0pQJegQIChAB&biw=1482&bih=856&dpr=1.25#fpstate=ive&vld=cid:af03c52d,vid:_IAjE_jUEOM,st:0)



