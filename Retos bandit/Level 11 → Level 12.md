# Objetivo
The password for the next level is stored in the file **data.txt**, where all lowercase (a-z) and uppercase (A-Z) letters have been rotated by 13 positions

# Datos de acceso al nivel
ssh bandit11@bandit.labs.overthewire.org -p 2220
6zPeziLdR2RKNdNYFNb6nVCKzphlXHBM

# Solución
```
bandit11@bandit:~$ whoami
bandit11
bandit11@bandit:~$ cat data.txt | base64 -d
␦�base64: invalid input
bandit11@bandit:~$ cat data.txt
Gur cnffjbeq vf WIAOOSFzMjXXBC0KoSKBbJ8puQm5lIEi
bandit11@bandit:~$ cat data.txt | tr [a-zA-Z] [n-za-mN-ZA-m]
The password is JVNBBFSmZwKKOP0XbFXOoW8chDz5yVRv
bandit11@bandit:~$ python3
Python 3.10.12 (main, Jun 11 2023, 05:26:28) [GCC 11.4.0] on linux
Type "help", "copyright", "credits" or "license" for more information.
>>> import codecs
>>> codecs.decode('Gur cnffjbeq vf WIAOOSFzMjXXBC0KoSKBbJ8puQm5lIEi','rot13')
'The password is JVNBBFSmZwKKOP0XbFXOoW8chDz5yVRv'
>>>
```
The password is JVNBBFSmZwKKOP0XbFXOoW8chDz5yVRv
# Notas adicionales

# Referencias