# Objetivo
There is a git repository at `ssh://bandit29-git@localhost/home/bandit29-git/repo` via the port `2220`. The password for the user `bandit29-git` is the same as for the user `bandit29`.

# Datos de acceso al nivel
ssh bandit29@bandit.labs.overthewire.org -p 2220
tQKvmcwNYcFS6vmPHIUSI3ShmsrQZK8S


# Solución
```
bandit29@bandit:~$ cd /tmp
bandit29@bandit:/tmp$ ls
ls: cannot open directory '.': Permission denied
bandit29@bandit:/tmp$ cd level29
bandit29@bandit:/tmp/level29$ ls
repo
bandit29@bandit:/tmp/level29$ cd repo
bandit29@bandit:/tmp/level29/repo$ ls
code  README.md
bandit29@bandit:/tmp/level29/repo$ cat README.md
# Bandit Notes
Some notes for bandit30 of bandit.

## credentials

- username: bandit30
- password: xbhV3HpNGlTIdnjUrdAlPzc2L6y9EOnS

bandit29@bandit:/tmp/level29/repo$
```

# Notas adicionales
 

# Referencias