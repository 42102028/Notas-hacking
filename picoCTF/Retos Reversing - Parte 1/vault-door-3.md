## Objetivo
This vault uses for-loops and byte arrays. The source code for this vault is here: [VaultDoor3.java](https://jupiter.challenges.picoctf.org/static/a4018cec1446761cb2e8cce05db925fa/VaultDoor3.java)

## Pistas
1. Make a table that contains each value of the loop variables and the corresponding buffer index that it writes to.


## Solución
```
let buffer = new Array(32);
const password = 'jU5t_a_sna_3lpm12g94c_u_4_m7ra41';

for (let i = 0; i < 8; i++) {
    buffer[i] = password[i];
}

for (let i = 8; i < 16; i++) {
    buffer[i] = password[23 - i];
}

for (let i = 16; i < 32; i += 2) {
    buffer[i] = password[46 - i];
}

for (let i = 31; i > 16; i -= 2) {
    buffer[i] = password[i];
}

console.log(`picoCTF{${buffer.join('')}}`);
```

picoCTF{jU5t_a_s1mpl3_an4gr4m_4_u_c79a21}

## Notas adicionales

## Referencias
https://captainmich.github.io/programming_language/CTF/Challenge/picoCTF2019/reverse_engineering.html#vault-door-3




