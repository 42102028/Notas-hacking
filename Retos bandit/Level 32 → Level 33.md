# Objetivo
After all this `git` stuff its time for another escape. Good luck!

# Datos de acceso al nivel
ssh bandit32@bandit.labs.overthewire.org -p 2220
rmCBvG56y58BXzv98yZGdO7ATVL5dW8y


# Solución
```
>> $0
$ echo $0
sh
$ ls -la
total 36
drwxr-xr-x  2 root     root      4096 Oct  5 06:19 .
drwxr-xr-x 70 root     root      4096 Oct  5 06:20 ..
-rw-r--r--  1 root     root       220 Jan  6  2022 .bash_logout
-rw-r--r--  1 root     root      3771 Jan  6  2022 .bashrc
-rw-r--r--  1 root     root       807 Jan  6  2022 .profile
-rwsr-x---  1 bandit33 bandit32 15128 Oct  5 06:19 uppershell
$ whoami
bandit33
$ id
uid=11033(bandit33) gid=11032(bandit32) groups=11032(bandit32)
$ cat /etc/bandit_pass/bandit33
odHo63fHiFqcWWJG9rLiLDtPm45KzUKy
$
```

# Notas adicionales
 

# Referencias