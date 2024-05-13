## Objetivo
Oracles can be your best friend, they will decrypt anything, except the flag's ciphertext. How will you break it? Connect with `nc mercury.picoctf.net 33780`.

## Pistas
1. What can you do with a different pair of ciphertext and plaintext? What if it is not so different after all...
## Solución
picoCTF{m4yb3_Th0se_m3s54g3s_4r3_difurrent_0801973}
```
arcf99-picoctf@webshell:~$ python problema.py 
[+] Opening connection to mercury.picoctf.net on port 33780: Done
/home/arcf99-picoctf/problema.py:5: BytesWarning: Text is not bytes; assuming ASCII, no guarantees. See https://docs.pwntools.com/#bytes
  print(r.recvuntil("n:"))
b'Welcome to the Padding Oracle Challenge\nThis oracle will take anything you give it and decrypt using RSA. It will not accept the ciphertext with the secret message... Good Luck!\n\n\nn:'
72403682266974813552409560864515881295763804044281279825454438411922313859270178430744522699172271129965580068046368127733349596037051198715679711502414873067496439489564064524707149287378182028156737857853328320415675220767990062255026244196302965102116718059445563497227383424636381071089468183818198655597
/home/arcf99-picoctf/problema.py:8: BytesWarning: Text is not bytes; assuming ASCII, no guarantees. See https://docs.pwntools.com/#bytes
  print(r.recvuntil("e:"))
b'e:'
65537
/home/arcf99-picoctf/problema.py:11: BytesWarning: Text is not bytes; assuming ASCII, no guarantees. See https://docs.pwntools.com/#bytes
  print(r.recvuntil("ciphertext:"))
b'ciphertext:'
45758648844242064276779739161903053502797267873074132341065309980228761064437094415127067464102822308009179850433988513415346313716127766860637296397855868615317582467680405960120910306056494997664458861565002510162161473854698103010334378153194289259800004208620340503829203017423112984458337454627357357492
/home/arcf99-picoctf/problema.py:14: BytesWarning: Text is not bytes; assuming ASCII, no guarantees. See https://docs.pwntools.com/#bytes
  print(r.recvuntil("to decrypt:"))
b'\n\nGive me ciphertext to decrypt:'
/home/arcf99-picoctf/problema.py:20: BytesWarning: Text is not bytes; assuming ASCII, no guarantees. See https://docs.pwntools.com/#bytes
  print(r.recvuntil("you go:"))
b' Here you go:'
580550060391700078946913236734911770139931497702556153513487440893406629034802718534645538074938502890768709712035489670906
290275030195850039473456618367455885069965748851278076756743720446703314517401359267322769037469251445384354856017744835453
b'picoCTF{m4yb3_Th0se_m3s54g3s_4r3_difurrent_0801973}'
[*] Closed connection to mercury.picoctf.net port 33780
```

```
from pwn import *
import binascii

r = remote("mercury.picoctf.net", 33780)
print(r.recvuntil("n:"))
n = int(r.recvline().strip())
print(n)
print(r.recvuntil("e:"))
e = int(r.recvline().strip())
print(e)
print(r.recvuntil("ciphertext:"))
c = int(r.recvline().strip())
print(c)
print(r.recvuntil("to decrypt:"))

# Realiza la operaci  n modificada sobre el cifrado y env  a el resultado
modified_ciphertext = (pow(2, e, n) * c) % n
r.sendline(str(modified_ciphertext).encode())  # Aseg  rate de enviar bytes

print(r.recvuntil("you go:"))
p2 = int(r.recvline().strip())
print(p2)

# Recuperando el mensaje original
original_message = p2 // 2
print(original_message)
st = "{:x}".format(original_message)
print(binascii.unhexlify(st.encode()))  # Convierte el hexadecimal a bytes y muestra

r.close()
```
## Notas adicionales

## Referencias
[(6299) picoCTF No Padding, No Problem - YouTube](https://www.youtube.com/watch?v=iFpLqVoFR08&t=50s)



