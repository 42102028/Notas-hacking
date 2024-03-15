## Objetivo
Find the flag in this [picture](https://jupiter.challenges.picoctf.org/static/916b07b4c87062c165ace1d3d31ef655/pico_img.png).

## Pistas
1. What does meta mean in the context of files?
2. Ever heard of metadata?

## Solución
```
arcf99-picoctf@webshell:~$ mkdir imagenSoMeta
arcf99-picoctf@webshell:~$ cd imagenSoMeta/
arcf99-picoctf@webshell:~/imagenSoMeta$ wget https://jupiter.challenges.picoctf.org/static/916b07b4c87062c165ace1d3d31ef655/pico_img.png
--2024-03-15 03:40:19--  https://jupiter.challenges.picoctf.org/static/916b07b4c87062c165ace1d3d31ef655/pico_img.png
Resolving jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)... 3.131.60.8
Connecting to jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)|3.131.60.8|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 108795 (106K) [application/octet-stream]
Saving to: 'pico_img.png'

pico_img.png                                             100%[=================================================================================================================================>] 106.25K  --.-KB/s    in 0.001s  

2024-03-15 03:40:19 (148 MB/s) - 'pico_img.png' saved [108795/108795]

arcf99-picoctf@webshell:~/imagenSoMeta$ ls         
pico_img.png
arcf99-picoctf@webshell:~/imagenSoMeta$ exiftool pico_img.png 
ExifTool Version Number         : 12.40
File Name                       : pico_img.png
Directory                       : .
File Size                       : 106 KiB
File Modification Date/Time     : 2020:10:26 18:38:23+00:00
File Access Date/Time           : 2024:03:15 03:40:19+00:00
File Inode Change Date/Time     : 2024:03:15 03:40:19+00:00
File Permissions                : -rw-rw-r--
File Type                       : PNG
File Type Extension             : png
MIME Type                       : image/png
Image Width                     : 600
Image Height                    : 600
Bit Depth                       : 8
Color Type                      : RGB
Compression                     : Deflate/Inflate
Filter                          : Adaptive
Interlace                       : Noninterlaced
Software                        : Adobe ImageReady
XMP Toolkit                     : Adobe XMP Core 5.3-c011 66.145661, 2012/02/06-14:56:27
Creator Tool                    : Adobe Photoshop CS6 (Windows)
Instance ID                     : xmp.iid:A5566E73B2B811E8BC7F9A4303DF1F9B
Document ID                     : xmp.did:A5566E74B2B811E8BC7F9A4303DF1F9B
Derived From Instance ID        : xmp.iid:A5566E71B2B811E8BC7F9A4303DF1F9B
Derived From Document ID        : xmp.did:A5566E72B2B811E8BC7F9A4303DF1F9B
Warning                         : [minor] Text/EXIF chunk(s) found after PNG IDAT (may be ignored by some readers)
Artist                          : picoCTF{s0_m3ta_d8944929}
Image Size                      : 600x600
Megapixels                      : 0.360
arcf99-picoctf@webshell:~/imagenSoMeta$ 
```

## Notas adicionales

## Referencias
[PicoCTF 2019 - So Meta (zomry1.github.io)](https://zomry1.github.io/so-meta/)



