Puntos: 50pts

# Objetivo del Nivel

Do you know how to use the web inspector?Start searching [here](http://titan.picoctf.net:53646/) to find the flag

# Pistas del Nivel

- Use the web inspector on other files included by the web page.
- The flag may or may not be encoded

# Solución/Resultado/Flag

```bash
en la barra de busqueda view-source:titan.picoctf.net:53646/about.html
esta esta linea  <section class="about" notify_true="cGljb0NURnt3ZWJfc3VjYzNzc2Z1bGx5X2QzYzBkZWRfMjgzZTYyZmV9">

picoCTF{web_succ3ssfully_d3c0ded_283e62fe}
```

picoCTF{web_succ3ssfully_d3c0ded_283e62fe}

# Notas Adicionales

# Referencias

https://play.picoctf.org/events/73/challenges?page=1&search=
