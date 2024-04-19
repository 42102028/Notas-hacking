## Objetivo
We found this weird message being passed around on the servers, we think we have a working decryption scheme.Download the message [here](https://artifacts.picoctf.net/c/129/message.txt).Take each number mod 37 and map it to the following character set: 0-25 is the alphabet (uppercase), 26-35 are the decimal digits, and 36 is an underscore.Wrap your decrypted message in the picoCTF flag format (i.e. `picoCTF{decrypted_message}`)

## Pistas
1. Do you know what `mod 37` means?
2. `mod 37` means modulo 37. It gives the remainder of a number after being divided by 37.

## Solución
picoCTF{R0UND_N_R0UND_ADD17EC2}

```
nums = [350, 63, 353, 198, 114, 369, 346, 184, 202, 322, 94, 235, 114, 110, 185, 188, 225, 212, 366, 374, 261, 213]

for num in nums :
    mod = num % 37
    if mod == 36 :
        print('_', end = '')
    elif mod >= 26 and mod <= 35 :
        print(str(mod-26), end = '')
    else :
        print(chr(mod + 65), end = '')
```

## Notas adicionales

## Referencias
https://velog.io/@helenason/picoCTF-basic-mod1-writeup



