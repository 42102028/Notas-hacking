Puntos: 75pts

# Objetivo del Nivel

Know of little and big endian?

Additional details will be available after launching your challenge instance.
# Pistas del Nivel

- You might want to check the ASCII table to first find the hexadecimal representation of characters before finding the endianness.
- Read more about how endianness [here](https://levelup.gitconnected.com/little-endian-and-big-endian-74ab6441b2a7)
# Solución/Resultado/Flag

```bash
ryuuisdead-picoctf@webshell:~/picoCFT2024/GeneralSkills/endiannes$ nc titan.picoctf.net 52854
Welcome to the Endian CTF!
You need to find both the little endian and big endian representations of a word.
If you get both correct, you will receive the flag.
Word: oobcy
Enter the Little Endian representation: 7963626F6F
Correct Little Endian representation!
Enter the Big Endian representation: 6f6f626379
Correct Big Endian representation!
Congratulations! You found both endian representations correctly!
Your Flag is: picoCTF{3ndi4n_sw4p_su33ess_28329f0a}
```

picoCTF{3ndi4n_sw4p_su33ess_28329f0a}

# Notas Adicionales

# Referencias

https://play.picoctf.org/events/73/challenges?page=1&search=
