# Objetivo
The password for the next level is stored in a hidden file in the **inhere** directory.

# Datos de acceso al nivel
ssh bandit3@bandit.labs.overthewire.org -p 2220
aBZ0W5EmUfAf7kHTQeOwd8bauFJ2lAiG

# Solución
```
bandit3@bandit:~$ ls
inhere
bandit3@bandit:~$ cd inhere
bandit3@bandit:~/inhere$ cd ..
bandit3@bandit:~$ cat inhere
cat: inhere: Is a directory
bandit3@bandit:~$ cd inhere
bandit3@bandit:~/inhere$ ls
bandit3@bandit:~/inhere$ ls
bandit3@bandit:~/inhere$ find
.
./.hidden
bandit3@bandit:~/inhere$ cat ./.hidden
2EW7BBsr6aMMoJ2HjW067dm8EgX26xNe
```

# Notas adicionales

# Referencias