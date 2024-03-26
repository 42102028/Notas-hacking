Puntos: 50pts

# Objetivo del Nivel

People keep trying to trick my players with imitation flags. I want to make sure they get the real thing! I'm going to provide the SHA-256 hash and a decrypt script to help you know that my flags are legitimate.You can download the challenge files here:

- `[challenge.zip](https://artifacts.picoctf.net/c_rhea/20/challenge.zip)`

Additional details will be available after launching your challenge instance.
# Pistas del Nivel

- Checksums let you tell if a file is complete and from the original distributor. If the hash doesn't match, it's a different file.
- You can create a SHA checksum of a file with `sha256sum <file>` or all files in a directory with `sha256sum <directory>/*`.
- Remember you can pipe the output of one command to another with `|`. Try practicing with the 'First Grep' challenge if you're stuck!

# Solución/Resultado/Flag

```bash
ryuuisdead-picoctf@webshell:~$ ssh -p 56188 ctf-player@rhea.picoctf.net
...
...
ctf-player@pico-chall$ ls
checksum.txt  decrypt.sh  files
ctf-player@pico-chall$ cat checksum.txt 
fba9f49bf22aa7188a155768ab0dfdc1f9b86c47976cd0f7c9003af2e20598f7
ctf-player@pico-chall$ sha256sum files/* | grep fba9f49bf22aa7188a155768ab0dfdc1f9b86c47976cd0f7c9003af2e20598f7
fba9f49bf22aa7188a155768ab0dfdc1f9b86c47976cd0f7c9003af2e20598f7  files/87590c24
ctf-player@pico-chall$ ./decrypt.sh files/87590c24
picoCTF{trust_but_verify_87590c24}
```

picoCTF{trust_but_verify_87590c24}

# Notas Adicionales

# Referencias

https://play.picoctf.org/events/73/challenges?page=1&search=
