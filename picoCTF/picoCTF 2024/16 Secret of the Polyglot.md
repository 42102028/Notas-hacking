Puntos: 100pts

# Objetivo del Nivel

The Network Operations Center (NOC) of your local institution picked up a suspicious file, they're getting conflicting information on what type of file it is. They've brought you in as an external expert to examine the file. Can you extract all the information from this strange file?Download the suspicious file [here](https://artifacts.picoctf.net/c_titan/96/flag2of2-final.pdf).
# Pistas del Nivel

- This problem can be solved by just opening the file in different ways
# Solución/Resultado/Flag

```bash
Se abre el archivo descargado, .pdf

janviier-picoctf@webshell:~/picoCTF$ wget https://artifacts.picoctf.net/c_titan/96/flag2of2-final.pdf
--2024-03-15 02:24:31--  https://artifacts.picoctf.net/c_titan/96/flag2of2-final.pdf
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 3.160.22.43, 3.160.22.16, 3.160.22.92, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|3.160.22.43|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 3362 (3.3K) [application/octet-stream]
Saving to: 'flag2of2-final.pdf'

flag2of2-final.pdf                                       100%[=================================================================================================================================>]   3.28K  --.-KB/s    in 0s      

2024-03-15 02:24:31 (1.47 GB/s) - 'flag2of2-final.pdf' saved [3362/3362]

janviier-picoctf@webshell:~/picoCTF$ ls
flag2of2-final.pdf
janviier-picoctf@webshell:~/picoCTF$ open flag2of2-final.pdf

1n_pn9_&_pdf_90974127}
```

```bash
y despues convertimos con la pista, el archivo pdf a .png

janviier-picoctf@webshell:~/picoCTF$ mv flag2of2-final.pdf flag2of2-final.png 
janviier-picoctf@webshell:~/picoCTF$ ls
flag2of2-final.png
janviier-picoctf@webshell:~/picoCTF$ open

picoCTF{f1u3n7_
```

picoCTF{f1u3n7_1n_pn9_&_pdf_90974127}

# Notas Adicionales

# Referencias

https://play.picoctf.org/events/73/challenges?page=1&search=
