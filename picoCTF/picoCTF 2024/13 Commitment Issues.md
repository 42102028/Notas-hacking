Puntos: 50pts

# Objetivo del Nivel

I accidentally wrote the flag down. Good thing I deleted it!You download the challenge files here:

- [challenge.zip](https://artifacts.picoctf.net/c_titan/136/challenge.zip)
# Pistas del Nivel

- Version control can help you recover files if you change or lose them!
- Read the chapter on Git from the picoPrimer [here](https://primer.picoctf.org/#_git_version_control)
- You can 'checkout' commits to see the files inside them

# Solución/Resultado/Flag

```bash

ryuuisdead-picoctf@webshell:~/picoCFT2024/GeneralSkills/commitmentissues$ cd drop-in/
ryuuisdead-picoctf@webshell:~/picoCFT2024/GeneralSkills/commitmentissues/drop-in$ git log
ryuuisdead-picoctf@webshell:~/picoCFT2024/GeneralSkills/commitmentissues/drop-in$ 
ryuuisdead-picoctf@webshell:~/picoCFT2024/GeneralSkills/commitmentissues/drop-in$ git checkout 87b85d7dfb839b077678611280fa023d76e017b8
Previous HEAD position was 8dc5180 remove sensitive info
HEAD is now at 87b85d7 create flag
ryuuisdead-picoctf@webshell:~/picoCFT2024/GeneralSkills/commitmentissues/drop-in$ ls
message.txt
ryuuisdead-picoctf@webshell:~/picoCFT2024/GeneralSkills/commitmentissues/drop-in$ cat message.txt 
picoCTF{s@n1t1z3_ea83ff2a}

```

picoCTF{s@n1t1z3_ea83ff2a}

# Notas Adicionales

# Referencias

https://play.picoctf.org/events/73/challenges?page=1&search=
