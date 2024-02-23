# Objetivo
The password for the next level can be retrieved by submitting the password of the current level to **port 30000 on localhost**.

# Datos de acceso al nivel
ssh bandit14@bandit.labs.overthewire.org -p 2220
fGrHPx402xGC7U7rXKDaxiWFTOiF0ENq


# Solución
```
bandit14@bandit:~$ ls
bandit14@bandit:~$ nc localhost 30000
fGrHPx402xGC7U7rXKDaxiWFTOiF0ENq
Correct!
jN2kgmIXJ6fShzhT2avhotn4Zcka6tnt


bandit14@bandit:~$ echo "fGrHPx402xGC7U7rXKDaxiWFTOiF0ENq" | nc localhost 30000
Correct!
jN2kgmIXJ6fShzhT2avhotn4Zcka6tnt

bandit14@bandit:~$

```

# Notas adicionales

# Referencias