## Objetivo
Find the flag being held on this server to get ahead of the competition [http://mercury.picoctf.net:53554/](http://mercury.picoctf.net:53554/)

## Pistas
1. Maybe you have more than 2 choices
2. Check out tools like Burpsuite to modify your requests and look at the responses

## Solución

1. Usamos Burp Suite para interceptar la solicitud de hacer clic en el botón "Elegir azul".
2. Cambie la solicitud POST a una solicitud HEAD
3. El HTML devuelto por la solicitud HEAD en el navegador estará vacío, pero en la pestaña Historial HTTP de Proxy en Burp Suite puede encontrar la bandera como encabezado HTTP en la respuesta:

picoCTF{r3j3ct_th3_du4l1ty_2e5ba39f}
## Notas adicionales

## Referencias