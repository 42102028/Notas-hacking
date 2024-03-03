## Objetivo
What does this `bDNhcm5fdGgzX3IwcDM1` mean? I think it has something to do with bases.

## Pistas
Submit your answer in our flag format. For example, if your answer was 'hello', you would submit 'picoCTF{hello}' as the flag.

## Solución
El texto `bDNhcm5fdGgzX3IwcDM1` es una cadena codificada en Base64. Al decodificarla, obtenemos el texto en claro: `l3arn_th3_r0p35`.

Supuse que el texto `bDNhcm5fdGgzX3IwcDM1` estaba en Base64 por su formato alfanumérico y longitud, común en este tipo de codificación

```
import base64 
# Base64 encoded string encoded_str = "bDNhcm5fdGgzX3IwcDM1" 
# Decode the string decoded_str = base64.b64decode(encoded_str).decode('utf-8') 
decoded_str
```

## Notas adicionales

## Referencias