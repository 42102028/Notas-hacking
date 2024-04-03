## Objetivo
Can you get the flag?Here's the [website](http://saturn.picoctf.net:55793/).We know that the website files live in `/usr/share/nginx/html/` and the flag is at `/flag.txt` but the website is filtering absolute file paths. Can you get past the filter to read the flag?

## Pistas
(None)

## Solución
En el sitio web, encontramos una lista de tres archivos de texto y se nos pidió que ingresáramos el nombre del archivo que queríamos leer. La descripción reveló que la bandera está almacenada en /flag.txt, pero el sitio web fue diseñado para filtrar rutas absolutas de archivos.

Para evitar este filtro, ideamos una estrategia. Primero necesitábamos navegar hasta el directorio raíz. Para lograr esto, volvimos atrás (..) y luego ingresamos flag.txt, creando la ruta ../../../../../flag.txt Este camino nos permitió acceder a la bandera y obtenerla.
## Notas adicionales

## Referencias



