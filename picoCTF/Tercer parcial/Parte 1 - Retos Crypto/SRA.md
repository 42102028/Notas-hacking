## Objetivo
I just recently learnt about the SRA public key cryptosystem... or wait, was it supposed to be RSA? Hmmm, I should probably check...

Additional details will be available after launching your challenge instance.

## Pistas
(None)

## Solución
picoCTF{7h053_51n5_4r3_n0_m0r3_0795e891}

usamos este codigo con los valores que nos da la conexion en SageMathCell, que es una interfaz web fácil de usar para un sistema de software matemático gratuito de código abierto, SageMath.

```
e = 65537
d = 22965306068311705113308489975941971960577533242015658110230927412291740815401
ct = 8431896924792372054158539816414604608245210456255042227632602513567500025410

phi = (e*d)-1

list = []
for a,b in factor(phi):
 for _ in range(b):
  list.append(a)

primes = []

print("factoing primes using combinations")
for i in range(len(list)):
 for comb in Combinations(list,i):
  prod = product(comb)
  if is_prime(prod + 1):
   prime = prod + 1
   if prime.nbits() == 128:
    primes.append(prime)

print(primes)
print("decrypting cipher")

for vals in Combinations(primes,2):
 n = product(vals)
 try:
  m = bytes.fromhex(hex(pow(ct,d,n))[2:]).decode()
  if m.isalnum():
   print(m)
   break
 except:
  pass
```

El código intenta descifrar un mensaje cifrado con RSA, buscando primos específicos de 128 bits que son candidatos para ser los factores del módulo 𝑛n a partir de la factorización de 𝜙=(𝑒⋅𝑑)−1ϕ=(e⋅d)−1. Luego, prueba combinaciones de estos primos para reconstruir posibles valores de 𝑛n, y utiliza el exponente privado 𝑑d para descifrar el texto cifrado 𝑐𝑡ct, buscando obtener un mensaje legible

```
arcf99-picoctf@webshell:~$ nc saturn.picoctf.net 59214
anger = 8431896924792372054158539816414604608245210456255042227632602513567500025410
envy = 22965306068311705113308489975941971960577533242015658110230927412291740815401
vainglory?
> kVjIRQ1AMuJGO5MM
kVjIRQ1AMuJGO5MM
Conquered!
picoCTF{7h053_51n5_4r3_n0_m0r3_0795e891}
```

## Notas adicionales

## Referencias
[Crypto Conspiracy | Part 4 | HTB: CA & PicoCTF 2023 | by Hussain | Medium](https://ain-kun.medium.com/crypto-conspiracy-part-4-htb-ca-picoctf-2023-2480a39b264f)
[Sage Cell Server (sagemath.org)](https://sagecell.sagemath.org/)


[Install from Source Code - Installation Guide (sagemath.org)](https://doc.sagemath.org/html/en/installation/source.html#sec-installation-from-sources)




