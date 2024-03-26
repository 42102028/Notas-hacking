Puntos: 50pts

# Objetivo del Nivel

Why search for the flag when I can make a bookmarklet to print it for me?Browse [here](http://titan.picoctf.net:51717/), and find the flag!

# Pistas del Nivel

- A bookmarklet is a bookmark that runs JavaScript instead of loading a webpage.
- What happens when you click a bookmarklet?
- Web browsers have other ways to run JavaScript too.

# Solución/Resultado/Flag

```bash
En la barra de direcciones buscar: 
    javascript: "codigo javascript"

Introducir javascript: seguido de código JavaScript en la barra de direcciones del navegador (también conocido como "URL de javascript") sirve para ejecutar código JavaScript directamente en la página web actualmente cargada.
Al poner código JavaScript precedido por javascript: en la barra de direcciones del navegador (o guardar este código como un favorito/marcador), estás creando un bookmarklet.
```

picoCTF{}

# Notas Adicionales

# Referencias

https://play.picoctf.org/events/73/challenges?page=1&search=
