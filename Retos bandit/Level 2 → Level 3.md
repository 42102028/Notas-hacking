# Objetivo
The password for the next level is stored in a file called **spaces in this filename** located in the home directory


# Datos de acceso al nivel
ssh bandit2@bandit.labs.overthewire.org -p 2220
rRGizSaX8Mk1RTb1CNQoXTcYZWU6lgzi

# Solución
```
bandit2@bandit:~$ ls
spaces in this filename
bandit2@bandit:~$ cat ./"spaces in this filename"
aBZ0W5EmUfAf7kHTQeOwd8bauFJ2lAiG
bandit2@bandit:~$
```

# Notas adicionales

# Referencias