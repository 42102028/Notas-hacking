## Objetivo
Not all ancient ciphers were so bad... The flag is not in standard format. `nc mercury.picoctf.net 33686` [playfair.py](https://mercury.picoctf.net/static/aec5fd7b1ec96307c4eda752a3353f68/playfair.py)

## Pistas
(none)
## Solución
dpksmue41bnyue84jlem2jhl9ux755


```
alphabet = 'v60ufmk7edg4z13h2oyqa9ib58ntwxlrscjp'
SQUARE_SIZE = 6

def generate_square(alphabet):
    assert len(alphabet) == SQUARE_SIZE ** 2, f"Alphabet must be of length {SQUARE_SIZE * SQUARE_SIZE}"
    matrix = [alphabet[i * SQUARE_SIZE:(i + 1) * SQUARE_SIZE] for i in range(SQUARE_SIZE)]
    return matrix

matrix = generate_square(alphabet)

index = {}
for i in range(6):
    for x in range(6):
        index[matrix[i][x]] = [i, x]

def split_by_two(text):
    splits = []
    for i in range(0, len(text), 2):
        splits.append(text[i] + text[i + 1])
    return splits

def get_rectangle(pair, index, matrix):
    p1 = index[pair[0]]
    p2 = index[pair[1]]
    
    if p1[0] == p2[0]:  # Same row
        return matrix[p1[0]][(p1[1] - 1) % SQUARE_SIZE] + matrix[p2[0]][(p2[1] - 1) % SQUARE_SIZE]
    elif p1[1] == p2[1]:  # Same column
        return matrix[(p1[0] - 1) % SQUARE_SIZE][p1[1]] + matrix[(p2[0] - 1) % SQUARE_SIZE][p2[1]]
    else:  # Rectangle
        return matrix[p1[0]][p2[1]] + matrix[p2[0]][p1[1]]

ciphertext = '4celvfdkoq5a0dx7pr40ifzctd8488'
splits = split_by_two(ciphertext)

plaintext = ''
for s in splits:
    plaintext += get_rectangle(s, index, matrix)

print(f'Decrypted: {plaintext}')

```

usamos el codigo anterior con los valores que nos da la conexion y nos da la bandera 
3a64de31e7b5acb6c87ae45050e187ee

## Notas adicionales

## Referencias
[CTFtime.org / picoCTF 2021 / Play nice / Writeup](https://ctftime.org/writeup/26980)



