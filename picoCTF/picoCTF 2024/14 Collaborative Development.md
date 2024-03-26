Puntos: 75pts

# Objetivo del Nivel

My team has been working very hard on new features for our flag printing program! I wonder how they'll work together?You can download the challenge files here:

- [challenge.zip](https://artifacts.picoctf.net/c_titan/176/challenge.zip)
# Pistas del Nivel

- `git branch -a` will let you see available branches
- How can file 'diffs' be brought to the main branch? Don't forget to `git config`!
- Merge conflicts can be tricky! Try a text editor like nano, emacs, or vim.

# Solución/Resultado/Flag

```bash
ryuuisdead-picoctf@webshell:~/picoCFT2024/GeneralSkills/CollaborativeDev$ unzip challenge.zip 
Archive:  challenge.zip
   creating: drop-in/
   creating: drop-in/.git/
   creating: drop-in/.git/branches/
ryuuisdead-picoctf@webshell:~/picoCFT2024/GeneralSkills/CollaborativeDev$ cd drop-in/
ryuuisdead-picoctf@webshell:~/picoCFT2024/GeneralSkills/CollaborativeDev/drop-in$ ls
flag.py
ryuuisdead-picoctf@webshell:~/picoCFT2024/GeneralSkills/CollaborativeDev/drop-in$ cat flag.py
print("Printing the flag...")
ryuuisdead-picoctf@webshell:~/picoCFT2024/GeneralSkills/CollaborativeDev/drop-in$ git branch -a
ryuuisdead-picoctf@webshell:~/picoCFT2024/GeneralSkills/CollaborativeDev/drop-in$ 
ryuuisdead-picoctf@webshell:~/picoCFT2024/GeneralSkills/CollaborativeDev/drop-in$ git checkout feature/part-1
Switched to branch 'feature/part-1'
ryuuisdead-picoctf@webshell:~/picoCFT2024/GeneralSkills/CollaborativeDev/drop-in$ cat flag.py 
print("Printing the flag...")

print("picoCTF{t3@mw0rk_", end='')
ryuuisdead-picoctf@webshell:~/picoCFT2024/GeneralSkills/CollaborativeDev/drop-in$ git checkout feature/part-2
Switched to branch 'feature/part-2'
ryuuisdead-picoctf@webshell:~/picoCFT2024/GeneralSkills/CollaborativeDev/drop-in$ cat flag.py 
print("Printing the flag...")

print("m@k3s_th3_dr3@m_", end='')
ryuuisdead-picoctf@webshell:~/picoCFT2024/GeneralSkills/CollaborativeDev/drop-in$ git checkout feature/part-3
Switched to branch 'feature/part-3'
ryuuisdead-picoctf@webshell:~/picoCFT2024/GeneralSkills/CollaborativeDev/drop-in$ cat flag.py 
print("Printing the flag...")

print("w0rk_2c91ca76}")

picoCTF{t3@mw0rk_m@k3s_th3_dr3@m_w0rk_2c91ca76}
```

picoCTF{t3@mw0rk_m@k3s_th3_dr3@m_w0rk_2c91ca76}

# Notas Adicionales

# Referencias

https://play.picoctf.org/events/73/challenges?page=1&search=
