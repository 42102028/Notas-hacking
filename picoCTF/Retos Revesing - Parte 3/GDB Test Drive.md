## Objetivo
Can you get the flag?Download this [binary](https://artifacts.picoctf.net/c/86/gdbme).Here's the test drive instructions:

- `$ chmod +x gdbme`
- `$ gdb gdbme`
- `(gdb) layout asm`
- `(gdb) break *(main+99)`
- `(gdb) run`
- `(gdb) jump *(main+104)`

## Pistas
(None)

## Solución
picoCTF{d3bugg3r_dr1v3_72bd8355}
En el desafío "GDB Test Drive" de PicoCTF, se utiliza GDB para analizar un programa en C que tiene un largo período de suspensión antes de imprimir una bandera. La solución implica establecer un punto de interrupción en la llamada a la función de suspensión y modificar la dirección de retorno para evitar la suspensión, lo que le permite saltar directamente a la parte del código que imprime la bandera.
## Notas adicionales

## Referencias
https://www.stackzero.net/picoctf-gdb-test-drive/



