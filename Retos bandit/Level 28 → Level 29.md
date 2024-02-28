# Objetivo
There is a git repository at `ssh://bandit28-git@localhost/home/bandit28-git/repo` via the port `2220`. The password for the user `bandit28-git` is the same as for the user `bandit28`.

# Datos de acceso al nivel
ssh bandit28@bandit.labs.overthewire.org -p 2220
AVanL161y9rsbcJIsFHuw35rjaOM19nR


# Solución
```
bandit28@bandit:/tmp/git_level28$ cd repo
-bash: cd: repo: No such file or directory
bandit28@bandit:/tmp/git_level28$ cd
bandit28@bandit:~$ mkdir level28
mkdir: cannot create directory ‘level28’: Permission denied
bandit28@bandit:~$ mkdir level28
mkdir: cannot create directory ‘level28’: Permission denied
bandit28@bandit:~$ cd /tmp/
bandit28@bandit:/tmp$ mkdir level28
mkdir: cannot create directory ‘level28’: File exists
bandit28@bandit:/tmp$ cd level28
bandit28@bandit:/tmp/level28$ ls
repo
bandit28@bandit:/tmp/level28$ cd repo
bandit28@bandit:/tmp/level28/repo$ ls
README.md
bandit28@bandit:/tmp/level28/repo$ cat README.md
# Bandit Notes
Some notes for level29 of bandit.

## credentials

- username: bandit29
- password: tQKvmcwNYcFS6vmPHIUSI3ShmsrQZK8S

bandit28@bandit:/tmp/level28/repo$

```

# Notas adicionales
 

# Referencias