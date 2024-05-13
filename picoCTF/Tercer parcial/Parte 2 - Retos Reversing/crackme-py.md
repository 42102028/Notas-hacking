## Objetivo
[crackme.py](https://mercury.picoctf.net/static/f440bf2510a28914afae2947749f2db0/crackme.py)

## Pistas
(None)

## Solución
picoCTF{1|\/|_4_p34|\|ut_8c551048}

Al observar detenidamente el código, encontramos que hay otra función que no se ejecuta porque nunca se llama. Entonces, cambiando el código y llamando a la función decode_secret(bezos_cc_secret), obtenemos nuestra bandera.


## Notas adicionales

## Referencias
[picoCTF write up: crackme-py - Arth Detroja - Medium](https://medium.com/@arthDetroja/picoctf-write-up-crackme-py-1bb568a3b3a3)



