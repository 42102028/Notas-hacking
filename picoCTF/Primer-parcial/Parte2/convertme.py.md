## Objetivo
Run the Python script and convert the given number from decimal to binary to get the flag.[Download Python script](https://artifacts.picoctf.net/c/22/convertme.py)

## Pistas
1. Look up a decimal to binary number conversion app on the web or use your computer's calculator!
2. The `str_xor` function does not need to be reverse engineered for this challenge.
3. If you have Python on your computer, you can download the script normally and run it. Otherwise, use the `wget` command in the webshell.
4. To use `wget` in the webshell, first right click on the download link and select 'Copy Link' or 'Copy Link Address'
5. Type everything after the dollar sign in the webshell: `$ wget` , then paste the link after the space after `wget` and press enter. This will download the script for you in the webshell so you can run it!
6. Finally, to run the script, type everything after the dollar sign and then press enter: `$ python3 convertme.py`

## Solución
La solución implica descargar el archivo `convertme.py` de un servidor remoto. Al ejecutar el script `convertme.py` con Python, se presenta un desafío que pide convertir el número 18 de base decimal a base binaria. Al responder correctamente con `10010`, el script devuelve la flag `picoCTF{4ll_y0ur_b4535_762f748e}`.

```
arcf99-picoctf@webshell:~/codebook$ mkdir convertme
arcf99-picoctf@webshell:~/codebook$ cd convertme
arcf99-picoctf@webshell:~/codebook/convertme$ wget https://artifacts.picoctf.net/c/22/convertme.py
--2024-03-03 21:09:56--  https://artifacts.picoctf.net/c/22/convertme.py
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 3.160.22.92, 3.160.22.43, 3.160.22.128, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|3.160.22.92|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 1189 (1.2K) [application/octet-stream]
Saving to: 'convertme.py'

convertme.py                                             100%[=================================================================================================================================>]   1.16K  --.-KB/s    in 0s      

2024-03-03 21:09:56 (24.6 MB/s) - 'convertme.py' saved [1189/1189]

arcf99-picoctf@webshell:~/codebook/convertme$ ls
convertme.py
arcf99-picoctf@webshell:~/codebook/convertme$ python convertme.py 
If 18 is in decimal base, what is it in binary base?
Answer: 10010
That is correct! Here's your flag: picoCTF{4ll_y0ur_b4535_762f748e}
```


## Notas adicionales

## Referencias
[Convertir Decimal a binario (prepostseo.com)](https://www.prepostseo.com/tool/es/decimal-to-binary-converter)