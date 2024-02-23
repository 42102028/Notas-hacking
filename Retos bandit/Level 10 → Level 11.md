# Objetivo
The password for the next level is stored in the file **data.txt**, which contains base64 encoded data

# Datos de acceso al nivel
ssh bandit10@bandit.labs.overthewire.org -p 2220
G7w8LIi6J3kTb8A7j9LgrywtEUlyyp6s


# Solución
```
bandit10@bandit:~$ cat data.txt | base64 -d
The password is 6zPeziLdR2RKNdNYFNb6nVCKzphlXHBM
```

# Notas adicionales

# Referencias
[CyberChef (gchq.github.io)](https://gchq.github.io/CyberChef/)