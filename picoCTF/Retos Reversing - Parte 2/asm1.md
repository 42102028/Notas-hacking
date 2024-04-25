## Objetivo
What does asm1(0x8be) return? Submit the flag as a hexadecimal value (starting with '0x'). NOTE: Your submission for this question will NOT be in the normal flag format. [Source](https://jupiter.challenges.picoctf.org/static/66c927e32f3d7be7a62d13a7c2250943/test.S)


## Pistas
1. assembly [conditions](https://www.tutorialspoint.com/assembly_programming/assembly_conditions.htm)


## Solución
0x8bb

La función asm1 con el argumento 0x8be realiza una serie de comparaciones y cálculos, finalmente retornando el valor 0x8bb en hexadecimal. Esto se debe a que el valor 0x8be cumple con la condición para no realizar un salto en la comparación específica y, posteriormente, se le resta 0x3 a este valor, resultando en 0x8bb.
## Notas adicionales

## Referencias
https://www.youtube.com/watch?v=uqsm_bcTMp8


