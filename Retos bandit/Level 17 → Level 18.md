# Objetivo
There are 2 files in the homedirectory: **passwords.old and passwords.new**. The password for the next level is in **passwords.new** and is the only line that has been changed between **passwords.old and passwords.new**

# Datos de acceso al nivel
ssh bandit17@bandit.labs.overthewire.org -p 2220
VwOSWtCA7lRKkTfbr2IDh6awj9RNZM5e

# Solución

```
bandit17@bandit:~$ ls
passwords.new  passwords.old
bandit17@bandit:~$ vc  -l passwords.old
vc: command not found
bandit17@bandit:~$
bandit17@bandit:~$ wc  -l passwords.old
100 passwords.old
bandit17@bandit:~$ diff passwords.old passwords.new --color
42c42
< p6ggwdNHncnmCNxuAt0KtKVq185ZU7AW
---
> hga5tuuCLF6fFzUpnagiMN8ssu9LFrdg
bandit17@bandit:~$ exit
```

# Notas adicionales
 

# Referencias