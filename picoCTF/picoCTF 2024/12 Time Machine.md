Puntos: 50pts

# Objetivo del Nivel

What was I last working on? I remember writing a note to help me remember...You can download the challenge files here:

- [challenge.zip](https://artifacts.picoctf.net/c_titan/160/challenge.zip)
# Pistas del Nivel

- The `cat` command will let you read a file, but that won't help you here!
- Read the chapter on Git from the picoPrimer [here](https://primer.picoctf.org/#_git_version_control).
- When committing a file with git, a message can (and should) be included.

# Solución/Resultado/Flag

```bash
ryuuisdead-picoctf@webshell:~/picoCFT2024/GeneralSkills/TimeMachine$ ls
challenge.zip  drop-in
ryuuisdead-picoctf@webshell:~/picoCFT2024/GeneralSkills/TimeMachine$ cd drop-in/
ryuuisdead-picoctf@webshell:~/picoCFT2024/GeneralSkills/TimeMachine/drop-in$ ls
message.txt
ryuuisdead-picoctf@webshell:~/picoCFT2024/GeneralSkills/TimeMachine/drop-in$ cat message.txt 
This is what I was working on, but Id need to look at my commit history to know why...ryuuisdead-picoctf@webshell:~/picoCFT2024/GeneralSkills/TimeMachine/drop-in$ 
ryuuisdead-picoctf@webshell:~/picoCFT2024/GeneralSkills/TimeMachine/drop-in$ git log
commit 89d296ef533525a1378529be66b22d6a2c01e530 (HEAD -> master)
Author: picoCTF <ops@picoctf.com>
Date:   Tue Mar 12 00:07:22 2024 +0000

picoCTF{t1m3m@ch1n3_186cd7d7}
```

picoCTF{t1m3m@ch1n3_186cd7d7}

# Notas Adicionales

# Referencias

https://play.picoctf.org/events/73/challenges?page=1&search=
