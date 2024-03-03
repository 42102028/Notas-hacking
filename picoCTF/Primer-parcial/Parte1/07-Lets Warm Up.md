## Objetivo
If I told you a word started with 0x70 in hexadecimal, what would it start with in ASCII?
## Pistas
Submit your answer in our flag format. For example, if your answer was 'hello', you would submit 'picoCTF{hello}' as the flag.

## Solución

'p'

```
 # Convert hex value to ASCII 
 hex_value = "0x70" 
 ascii_character = chr(int(hex_value, 16)) 
 ascii_character
 
```

## Notas adicionales

## Referencias



