## Objetivo
What does asm2(0xb,0x2e) return? Submit the flag as a hexadecimal value (starting with '0x'). NOTE: Your submission for this question will NOT be in the normal flag format. [Source](https://jupiter.challenges.picoctf.org/static/717467c8c8b4332ea5873ad8fe7b2dad/test.S)


## Pistas
1. assembly [conditions](https://www.tutorialspoint.com/assembly_programming/assembly_conditions.htm)


## Solución
0xf6

considerando los valores iniciales 0xb (11 en decimal) y 0x2e (46 en decimal):

1. **Configuración inicial**:
    
    - La función prepara el marco de pila y almacena espacio para variables locales.
2. **Almacenamiento de argumentos**:
    
    - El segundo argumento (0x2e, o 46 decimal) se almacena en la localidad `[ebp-0x4]`.
    - El primer argumento (0xb, o 11 decimal) se almacena en la localidad `[ebp-0x8]`.
3. **Estructura del bucle**:
    
    - La función entra en un bucle donde primero verifica si el valor en `[ebp-0x8]` (iniciando en 11) es menor o igual a 25587 (`0x63f3`).
    - Dentro del bucle, cada iteración incrementa el valor en `[ebp-0x4]` por 1 y disminuye el valor en `[ebp-0x8]` por 128.
4. **Condiciones del bucle**:
    
    - El bucle continúa hasta que el valor en `[ebp-0x8]` supera 25587.
    - Inicia en 11 y aumenta en 128 cada vez, necesitando aproximadamente 200 iteraciones para superar 25587.
5. **Finalización**:
    
    - Una vez que el bucle termina, el valor en `[ebp-0x4]`, que comenzó en 46 y fue incrementado en cada iteración del bucle, resulta en 246.
6. **Retorno**:
    
    - La función retorna el valor final de `[ebp-0x4]`, que es 246 decimal, equivalente a `0xf6` en hexadecimal.

En resumen, `asm2(0xb, 0x2e)` procesa y modifica los valores a través de un bucle controlado por incrementos y comparaciones, resultando en un valor final de `0xf6` al completar el bucle.
## Notas adicionales

## Referencias


