# Objetivo
The password for the next level is stored in a file called **readme** located in the home directory. Use this password to log into bandit1 using SSH. Whenever you find a password for a level, use SSH (on port 2220) to log into that level and continue the game.

# Datos de acceso al nivel
ssh bandit1@bandit.labs.overthewire.org -p 2220
NH2SXQwcBdpmTEzi3bvBHMM9H66vVXjL

# Solución
```
bandit1@bandit:~$ ls
-
bandit1@bandit:~$ cat .-
cat: .-: No such file or directory
bandit1@bandit:~$ cat ./-
rRGizSaX8Mk1RTb1CNQoXTcYZWU6lgzi
bandit1@bandit:~$
```

# Notas adicionales

# Referencias