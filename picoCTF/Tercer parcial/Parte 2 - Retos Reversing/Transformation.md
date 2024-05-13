## Objetivo
I wonder what this really is... [enc](https://mercury.picoctf.net/static/dd6004f51362ff76f98cb8c699510f23/enc) `''.join([chr((ord(flag[i]) << 8) + ord(flag[i + 1])) for i in range(0, len(flag), 2)])`

## Pistas
1. You may find some decoders online

## Solución
 picoCTF{16_bits_inst34d_of_8_0ddcd97a}
```
arcf99-picoctf@webshell:~/tercerParial$ ls
enc
arcf99-picoctf@webshell:~/tercerParial$ cat enc
灩捯䍔䙻ㄶ形楴獟楮獴㌴摟潦弸弰摤捤㤷慽arcf99-picoctf@webshell:~/tercerParial$ 
arcf99-picoctf@webshell:~/tercerParial$ touch script.py
arcf99-picoctf@webshell:~/tercerParial$ nano script.py 
arcf99-picoctf@webshell:~/tercerParial$ python3 script.py enc 
Flag: picoCTF{16_bits_inst34d_of_8_0ddcd97a}
arcf99-picoctf@webshell:~/tercerParial$ 
```

```
encoded_flag = open("enc").read()  
flag = ""  
for i in range(0, len(encoded_flag)):  
character1 = chr((ord(encoded_flag[i]) >> 8))  
character2 = chr(encoded_flag[i].encode('utf-16be')[-1])  
flag += character1  
flag += character2  
  
print("Flag: " + flag)
```
## Notas adicionales

## Referencias
[pico CTF- Transformation writeups | by CYber VIaz | Medium](https://medium.com/@CYberVIaz/pico-ctf-transformation-writeups-a5496cb3377b)



