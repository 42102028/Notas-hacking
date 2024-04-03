## Objetivo
Can you get the flag?Go to this [website](http://saturn.picoctf.net:50920/) and see what you can discover.

## Pistas
1. How is the password checked on this website?

## Solución
picoCTF{j5_15_7r4n5p4r3n7_05df90c8}

Mirando en Inspector y depurador (Fuentes) no encontramos nada útil. Probeando con variables ficticias. Utilizo admin, admin como nombre de usuario y contraseña respectivamente.
Ahora redirige a la página login.php. Al buscar en la pestaña del inspector, encontramos la función checkPassword(). Al buscar en el panel del depurador, encuentro Secure.js que contenía:

De la figura anterior se desprende que el nombre de usuario es "admin" como habíamos adivinado y la contraseña es: strongPassword098765.
## Notas adicionales

## Referencias



