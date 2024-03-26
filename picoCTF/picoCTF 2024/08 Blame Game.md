Puntos: 75pts

# Objetivo del Nivel

Someone's commits seems to be preventing the program from working. Who is it?You can download the challenge files here:

- [challenge.zip](https://artifacts.picoctf.net/c_titan/156/challenge.zip)

# Pistas del Nivel

- In collaborative projects, many users can make many changes. How can you see the changes within one file?
- Read the chapter on Git from the picoPrimer [here](https://primer.picoctf.org/#_git_version_control).
- You can use `python3 <file>.py` to try running the code, though you won't need to for this challenge.

# Solución/Resultado/Flag

```bash
Cuando abrí el archivo zip, tenía una carpeta git que contenía muchas otras carpetas. Simplemente localicé el que decía
logs porque supuse que ahí es donde encontraría la bandera. Dentro de la carpeta, había un archivo con la etiqueta "HEAD" que abrí en
bloc de notas y dentro del archivo, había muchos registros para cada confirmación. El segundo registro del registro superior mostraba la bandera.

Bandera: picoCTF{@sk_th3_1nt3rn_d2d29f22}
```

picoCTF{caesar_d3cr9pt3d_a47c6d69}

# Notas Adicionales

# Referencias

https://play.picoctf.org/events/73/challenges?page=1&search=
