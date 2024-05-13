## Objetivo
[keygenme-trial.py](https://mercury.picoctf.net/static/0c363291c47477642c72630d68936e50/keygenme-trial.py)

## Pistas
(None)

## Solución
picoCTF{1n_7h3_|<3y_of_75fc1081}

```
import hashlib

bUsername_trial = b"MORTON"
key_part_dynamic1_trial = ""

indices = [4,5,3,6,2,7,1,8]

for i in indices:
  key_part_dynamic1_trial += hashlib.sha256(bUsername_trial).hexdigest()[i]

key_part_static1_trial = "picoCTF{1n_7h3_|<3y_of_"

key_part_static2_trial = "}"
key_full_template_trial = key_part_static1_trial + key_part_dynamic1_trial + key_part_static2_trial

print(key_full_template_trial)
```

## Notas adicionales

## Referencias
[picoCTF keygenme-py writeup (github.com)](https://gist.github.com/TeckNick80/a771963d196836bac94467c11b8668da)



