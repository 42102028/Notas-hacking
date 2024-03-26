Puntos: 50pts

# Objetivo del Nivel

Are overflows just a stack concern?Download the binary [here](https://artifacts.picoctf.net/c_tethys/28/chall).Download the source [here](https://artifacts.picoctf.net/c_tethys/28/chall.c).

Additional details will be available after launching your challenge instance.

# Pistas del Nivel

- What part of the heap do you have control over and how far is it from the safe_var?

# Solución/Resultado/Flag

```bash
La solución a este desafío requirió que investigara el código fuente proporcionado. El código fuente indica que la memoria asignada
para input_data era 64, por lo que el búfer que escribí tenía 32 caracteres. Esto rompió el montón imprimiendo la bandera.

picoCTF{my_first_heap_overflow_76775c7c}
```

picoCTF{my_first_heap_overflow_76775c7c}

# Notas Adicionales

# Referencias

https://play.picoctf.org/events/73/challenges?page=1&search=
