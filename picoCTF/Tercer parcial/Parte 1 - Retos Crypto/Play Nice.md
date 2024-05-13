## Objetivo
Not all ancient ciphers were so bad... The flag is not in standard format. `nc mercury.picoctf.net 33686` [playfair.py](https://mercury.picoctf.net/static/aec5fd7b1ec96307c4eda752a3353f68/playfair.py)

## Pistas
(none)
## Solución
3a64de31e7b5acb6c87ae45050e187ee


```
#!/usr/bin/python3 -u
import signal

SQUARE_SIZE = 6

def generate_square(alphabet):
    assert len(alphabet) == pow(SQUARE_SIZE, 2), "Alphabet must be of length " + str(SQUARE_SIZE * SQUARE_SIZE)
    matrix = []
    for i, letter in enumerate(alphabet):
        if i % SQUARE_SIZE == 0:
            row = []
        row.append(letter)
        if i % SQUARE_SIZE == (SQUARE_SIZE - 1):
            matrix.append(row)
    return matrix

def get_index(letter, matrix):
    for row in range(SQUARE_SIZE):
        for col in range(SQUARE_SIZE):
            if matrix[row][col] == letter:
                return (row, col)
    print("letter not found in matrix.")
    exit()

def decrypt_pair(pair, matrix):
    p1 = get_index(pair[0], matrix)
    p2 = get_index(pair[1], matrix)

    if p1[0] == p2[0]:
        return matrix[p1[0]][(p1[1] - 1) % SQUARE_SIZE] + matrix[p2[0]][(p2[1] - 1) % SQUARE_SIZE]
    elif p1[1] == p2[1]:
        return matrix[(p1[0] - 1) % SQUARE_SIZE][p1[1]] + matrix[(p2[0] - 1) % SQUARE_SIZE][p2[1]]
    else:
        return matrix[p1[0]][p2[1]] + matrix[p2[0]][p1[1]]

def decrypt_string(s, matrix):
    result = ""
    for i in range(0, len(s), 2):
        result += decrypt_pair(s[i:i+2], matrix)
    return result

def main():
    alphabet = "v60ufmk7edg4z13h2oyqa9ib58ntwxlrscjp"
    matrix = generate_square(alphabet)
    encrypted_message = "4celvfdkoq5a0dx7pr40ifzctd8488"
    decrypted_message = decrypt_string(encrypted_message, matrix)
    print("Decrypted message:", decrypted_message)

if __name__ == "__main__":
    signal.alarm(18)
    main()

```


## Notas adicionales

## Referencias



