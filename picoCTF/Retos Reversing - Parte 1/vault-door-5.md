## Objetivo
In the last challenge, you mastered octal (base 8), decimal (base 10), and hexadecimal (base 16) numbers, but this vault door uses a different change of base as well as URL encoding! The source code for this vault is here: [VaultDoor5.java](https://jupiter.challenges.picoctf.org/static/9505cca05dc00fecead41106370ee619/VaultDoor5.java)


## Pistas
1. You may find an encoder/decoder tool helpful, such as https://encoding.tools/
2. Read the wikipedia articles on URL encoding and base 64 encoding to understand how they work and what the results look like.


## Solución
```
picoCTF{c0nv3rt1ng_fr0m_ba5e_64_84fd5095}


import base64
from urllib import unquote
rawData = "JTYzJTMwJTZlJTc2JTMzJTcyJTc0JTMxJTZlJTY3JTVmJTY2JTcyJTMwJTZkJTVmJTYyJTYxJTM1JTY1JTVmJTM2JTM0JTVmJTM4JTM0JTY2JTY0JTM1JTMwJTM5JTM1"
flag = unquote(base64.b64decode(rawData))
print(flag)

```


## Notas adicionales

## Referencias
https://kamransaifullah.medium.com/picoctf-2019-reverse-engineering-vaultdoors-90486a89d812




