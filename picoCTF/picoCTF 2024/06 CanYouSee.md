Puntos: 50pts

# Objetivo del Nivel

How about some hide and seek?Download this file [here](https://artifacts.picoctf.net/c_titan/128/unknown.zip).

# Pistas del Nivel

- How can you view the information about the picture?
- If something isn't in the expected form, maybe it deserves attention?

# Solución/Resultado/Flag

```bash
''' exiftool ukn_reality.jpg '''
Este comando muestra información detallada de metadatos incrustada en el jpg, como la configuración de la cámara, la fecha de creación, las coordenadas GPS (si están disponibles) y más.
En los detalles, la URL de atribución me llamó la atención porque parecía texto base64.
URL de atribución: cGljb0NURntNRTc0RDQ3QV9ISUREM05fNGRhYmRkY2J9Cg==
Copié la URL y la decodifiqué en un descifrador base64 y me dio la bandera

picoCTF{ME74D47A_HIDD3N_3b9209a2}
```

picoCTF{ME74D47A_HIDD3N_3b9209a2}

# Notas Adicionales

# Referencias

https://play.picoctf.org/events/73/challenges?page=1&search=
