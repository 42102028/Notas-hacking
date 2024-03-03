## Objetivo
This website can be rendered only by **picobrowser**, go and catch the flag! `https://jupiter.challenges.picoctf.org/problem/28921/` ([link](https://jupiter.challenges.picoctf.org/problem/28921/)) or http://jupiter.challenges.picoctf.org:28921

## Pistas

## Solución
Ya que no estamos entrando con el navegador adecuado, usamos un comando que utiliza `curl` para hacer una petición a una URL específica, simulando el navegador "picobrowser" mediante el cambio del "User-Agent". Luego, filtra la respuesta con `grep` para buscar y mostrar cualquier línea que contenga "picoH", buscando así encontrar y mostrar la flag de picoCTF

![[Pasted image 20240302233218.png]]

## Notas adicionales

## Referencias