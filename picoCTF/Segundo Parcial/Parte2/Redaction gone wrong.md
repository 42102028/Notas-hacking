## Objetivo

Now you DON’T see me.This [report](https://artifacts.picoctf.net/c/84/Financial_Report_for_ABC_Labs.pdf) has some critical data in it, some of which have been redacted correctly, while some were not. Can you find an important key that was not redacted properly?
## Pistas
1. How can you be sure of the redaction?

## Solución
```
                                                                                                                   
┌──(kali㉿kali)-[~/…/retosForensic/segundoParcial/parte2/redactionGoneWrong]
└─$ wget https://artifacts.picoctf.net/c/84/Financial_Report_for_ABC_Labs.pdf
--2024-04-03 00:29:17--  https://artifacts.picoctf.net/c/84/Financial_Report_for_ABC_Labs.pdf
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 3.161.55.61, 3.161.55.64, 3.161.55.100, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|3.161.55.61|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 34915 (34K) [application/octet-stream]
Saving to: ‘Financial_Report_for_ABC_Labs.pdf’

Financial_Report_for_ABC_Lab 100%[=============================================>]  34.10K  --.-KB/s    in 0.06s   

2024-04-03 00:29:17 (609 KB/s) - ‘Financial_Report_for_ABC_Labs.pdf’ saved [34915/34915]

                                                                                                                   
┌──(kali㉿kali)-[~/…/retosForensic/segundoParcial/parte2/redactionGoneWrong]
└─$ ls
Financial_Report_for_ABC_Labs.pdf
                                                                                                                   
┌──(kali㉿kali)-[~/…/retosForensic/segundoParcial/parte2/redactionGoneWrong]
└─$ pdftotext Financial_Report_for_ABC_Labs.pdf 
Command 'pdftotext' not found, but can be installed with:
sudo apt install poppler-utils
Do you want to install it? (N/y)y
sudo apt install poppler-utils
[sudo] password for kali: 
Reading package lists... Done
Building dependency tree... Done
Reading state information... Done
The following NEW packages will be installed:
  poppler-utils
0 upgraded, 1 newly installed, 0 to remove and 472 not upgraded.
Need to get 192 kB of archives.
After this operation, 734 kB of additional disk space will be used.
Get:1 http://http.kali.org/kali kali-rolling/main amd64 poppler-utils amd64 22.12.0-2+b1 [192 kB]
Fetched 192 kB in 1s (250 kB/s)       
Selecting previously unselected package poppler-utils.
(Reading database ... 404070 files and directories currently installed.)
Preparing to unpack .../poppler-utils_22.12.0-2+b1_amd64.deb ...
Unpacking poppler-utils (22.12.0-2+b1) ...
Setting up poppler-utils (22.12.0-2+b1) ...
Processing triggers for man-db (2.12.0-3) ...
Processing triggers for kali-menu (2023.4.7) ...
                                                                                                                   
┌──(kali㉿kali)-[~/…/retosForensic/segundoParcial/parte2/redactionGoneWrong]
└─$ ls
Financial_Report_for_ABC_Labs.pdf
                                                                                                                   
┌──(kali㉿kali)-[~/…/retosForensic/segundoParcial/parte2/redactionGoneWrong]
└─$ pdftotext Financial_Report_for_ABC_Labs.pdf
                                                                                                                   
┌──(kali㉿kali)-[~/…/retosForensic/segundoParcial/parte2/redactionGoneWrong]
└─$ ls
Financial_Report_for_ABC_Labs.pdf  Financial_Report_for_ABC_Labs.txt
                                                                                                                                                                              
┌──(kali㉿kali)-[~/…/retosForensic/segundoParcial/parte2/redactionGoneWrong]
└─$ cat Financial_Report_for_ABC_Labs.txt | grep -o "picoCTF{.*}"           
picoCTF{C4n_Y0u_S33_m3_fully}
                                                                                                                   
┌──(kali㉿kali)-[~/…/retosForensic/segundoParcial/parte2/redactionGoneWrong]
└─$ 

```

Para extraer la flag del PDF, seguiste estos pasos:

1. **Descargaste el PDF** con `wget`.
2. **Convertiste el PDF a texto** usando `pdftotext`, una herramienta que tras instalar `poppler-utils`, permite pasar el contenido de un archivo PDF a un archivo de texto plano.
3. **Buscaste la flag** en el archivo de texto convertido utilizando `grep -o "picoCTF{.*}"`, lo que filtra y muestra solo las partes del texto que coinciden con el patrón de la flag de picoCTF
## Notas adicionales

## Referencias
https://ctftime.org/writeup/33112



