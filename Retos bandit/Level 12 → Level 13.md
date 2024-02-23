# Objetivo
The password for the next level is stored in the file **data.txt**, which is a hexdump of a file that has been repeatedly compressed. For this level it may be useful to create a directory under /tmp in which you can work using mkdir. For example: mkdir /tmp/myname123. Then copy the datafile using cp, and rename it using mv (read the manpages!)
# Datos de acceso al nivel
ssh bandit12@bandit.labs.overthewire.org -p 2220
JVNBBFSmZwKKOP0XbFXOoW8chDz5yVRv

# Solución
```
bandit12@bandit:~$ whoami
bandit12
bandit12@bandit:~$ ls
data.txt
bandit12@bandit:~$ cat
.bash_logout  .bashrc       data.txt      .profile
bandit12@bandit:~$ cat data.txt
00000000: 1f8b 0808 6855 1e65 0203 6461 7461 322e  ....hU.e..data2.
00000010: 6269 6e00 013d 02c2 fd42 5a68 3931 4159  bin..=...BZh91AY
00000020: 2653 5948 1b32 0200 0019 ffff faee cff7  &SYH.2..........
00000030: f6ff e4f7 bfbc ffff bff7 ffb9 39ff 7ffb  ............9...
00000040: bd31 eeff b9fb fbbb b9bf f77f b001 3b2c  .1............;,
00000050: d100 0d03 d200 6868 0d00 0069 a00d 0340  ......hh...i...@
00000060: 1a68 00d0 0d01 a1a0 0001 a680 0003 46d4  .h............F.
00000070: 6434 3234 611a 340d 07a4 c351 068f 5000  d424a.4....Q..P.
00000080: 069a 0680 0000 0006 8006 8da4 681a 6868  ............h.hh
00000090: 0d06 8d00 6834 3400 d07a 9a00 01a0 0341  ....h44..z.....A
000000a0: ea1e a190 da40 3d10 ca68 3468 6800 00c8  .....@=..h4hh...
000000b0: 1a1a 1b50 0683 d434 d069 a0d0 3100 d000  ...P...4.i..1...
000000c0: 001e a680 00d0 1a00 d0d0 6864 d0c4 d0d0  ..........hd....
000000d0: 000c 8641 7440 0108 032e 86b4 4cf0 22bb  ...At@......L.".
000000e0: 6682 2b7e b3e2 e98d aa74 dacc 0284 330d  f.+~.....t....3.
000000f0: bbb2 9494 d332 d933 642a 3538 d27e 09ce  .....2.3d*58.~..
00000100: 53da 185a 505e aada 6c75 59a2 b342 0572  S..ZP^..luY..B.r
00000110: 249a 4600 5021 25b0 1973 c18a 6881 1bef  $.F.P!%..s..h...
00000120: 3f9b 1429 5b1d 3d87 68b5 804f 1d28 42fa  ?..)[.=.h..O.(B.
00000130: 16c2 3241 98fb 8229 e274 5a63 fe92 3aca  ..2A...).tZc..:.
00000140: 70c3 a329 d21f 41e0 5a10 08cb 888f 30df  p..)..A.Z.....0.
00000150: f3da ce85 418b 0379 6a65 cfa2 eeb7 9f01  ....A..yje......
00000160: 782c da0e 288b e0c3 fe13 7af5 45ab 2b22  x,..(.....z.E.+"
00000170: a432 bf2f e32d b9e6 1465 2296 d805 a45e  .2./.-...e"....^
00000180: d1c1 eacb 7483 6aac ca0e cf24 8864 bd40  ....t.j....$.d.@
00000190: 118c 644a 1dc6 a127 375c b7a6 c124 bdae  ..dJ...'7\...$..
000001a0: 6d31 63a0 a223 3ea0 61d4 bdf0 450f 56fb  m1c..#>.a...E.V.
000001b0: a546 8d34 08a2 4f1d 43d3 9063 404d dd43  .F.4..O.C..c@M.C
000001c0: b4f2 e65d bcb7 5932 0f5e 6802 3892 a988  ...]..Y2.^h.8...
000001d0: 443d 8e89 7e09 4fb0 499d ee4e 4470 46c0  D=..~.O.I..NDpF.
000001e0: 2ba6 7c62 234a 7f76 151b aec0 23ee 4a97  +.|b#J.v....#.J.
000001f0: bc64 e34c de8a 5724 a1c3 9b89 cd96 1879  .d.L..W$.......y
00000200: d560 0cbb 5c26 09e4 efaf 5b94 402a 7780  .`..\&....[.@*w.
00000210: 4d87 30ce b8a3 946e 72c1 a643 1db7 a060  M.0....nr..C...`
00000220: 6524 629c 0c7e 8e7b e0f8 820c d5cb 60a0  e$b..~.{......`.
00000230: 003c a584 d4c1 61ef eb02 3f65 3a54 a3a2  .<....a...?e:T..
00000240: a565 c154 34c2 b162 d206 1ff8 bb92 29c2  .e.T4..b......).
00000250: 8482 40d9 9010 b3a9 e478 3d02 0000       ..@......x=...
bandit12@bandit:~$ ls- -la
Command 'ls-' not found, did you mean:
  command 'lsd' from snap lsd (0.16.0)
  command 'lsc' from deb livescript (1.6.1+dfsg-2)
  command 'ls' from deb coreutils (8.32-4.1ubuntu1)
  command 'lsw' from deb suckless-tools (46-1)
  command 'lsm' from deb lsm (1.0.4-2)
  command 'lsh' from deb lsh-client (2.1-13)
See 'snap info <snapname>' for additional versions.
bandit12@bandit:~$ ls -la
total 24
drwxr-xr-x  2 root     root     4096 Oct  5 06:19 .
drwxr-xr-x 70 root     root     4096 Oct  5 06:20 ..
-rw-r--r--  1 root     root      220 Jan  6  2022 .bash_logout
-rw-r--r--  1 root     root     3771 Jan  6  2022 .bashrc
-rw-r-----  1 bandit13 bandit12 2582 Oct  5 06:19 data.txt
-rw-r--r--  1 root     root      807 Jan  6  2022 .profile
bandit12@bandit:~$ xxd .profile
00000000: 2320 7e2f 2e70 726f 6669 6c65 3a20 6578  # ~/.profile: ex
00000010: 6563 7574 6564 2062 7920 7468 6520 636f  ecuted by the co
00000020: 6d6d 616e 6420 696e 7465 7270 7265 7465  mmand interprete
00000030: 7220 666f 7220 6c6f 6769 6e20 7368 656c  r for login shel
00000040: 6c73 2e0a 2320 5468 6973 2066 696c 6520  ls..# This file
00000050: 6973 206e 6f74 2072 6561 6420 6279 2062  is not read by b
00000060: 6173 6828 3129 2c20 6966 207e 2f2e 6261  ash(1), if ~/.ba
00000070: 7368 5f70 726f 6669 6c65 206f 7220 7e2f  sh_profile or ~/
00000080: 2e62 6173 685f 6c6f 6769 6e0a 2320 6578  .bash_login.# ex
00000090: 6973 7473 2e0a 2320 7365 6520 2f75 7372  ists..# see /usr
000000a0: 2f73 6861 7265 2f64 6f63 2f62 6173 682f  /share/doc/bash/
000000b0: 6578 616d 706c 6573 2f73 7461 7274 7570  examples/startup
000000c0: 2d66 696c 6573 2066 6f72 2065 7861 6d70  -files for examp
000000d0: 6c65 732e 0a23 2074 6865 2066 696c 6573  les..# the files
000000e0: 2061 7265 206c 6f63 6174 6564 2069 6e20   are located in
000000f0: 7468 6520 6261 7368 2d64 6f63 2070 6163  the bash-doc pac
00000100: 6b61 6765 2e0a 0a23 2074 6865 2064 6566  kage...# the def
00000110: 6175 6c74 2075 6d61 736b 2069 7320 7365  ault umask is se
00000120: 7420 696e 202f 6574 632f 7072 6f66 696c  t in /etc/profil
00000130: 653b 2066 6f72 2073 6574 7469 6e67 2074  e; for setting t
00000140: 6865 2075 6d61 736b 0a23 2066 6f72 2073  he umask.# for s
00000150: 7368 206c 6f67 696e 732c 2069 6e73 7461  sh logins, insta
00000160: 6c6c 2061 6e64 2063 6f6e 6669 6775 7265  ll and configure
00000170: 2074 6865 206c 6962 7061 6d2d 756d 6173   the libpam-umas
00000180: 6b20 7061 636b 6167 652e 0a23 756d 6173  k package..#umas
00000190: 6b20 3032 320a 0a23 2069 6620 7275 6e6e  k 022..# if runn
000001a0: 696e 6720 6261 7368 0a69 6620 5b20 2d6e  ing bash.if [ -n
000001b0: 2022 2442 4153 485f 5645 5253 494f 4e22   "$BASH_VERSION"
000001c0: 205d 3b20 7468 656e 0a20 2020 2023 2069   ]; then.    # i
000001d0: 6e63 6c75 6465 202e 6261 7368 7263 2069  nclude .bashrc i
000001e0: 6620 6974 2065 7869 7374 730a 2020 2020  f it exists.
000001f0: 6966 205b 202d 6620 2224 484f 4d45 2f2e  if [ -f "$HOME/.
00000200: 6261 7368 7263 2220 5d3b 2074 6865 6e0a  bashrc" ]; then.
00000210: 092e 2022 2448 4f4d 452f 2e62 6173 6872  .. "$HOME/.bashr
00000220: 6322 0a20 2020 2066 690a 6669 0a0a 2320  c".    fi.fi..#
00000230: 7365 7420 5041 5448 2073 6f20 6974 2069  set PATH so it i
00000240: 6e63 6c75 6465 7320 7573 6572 2773 2070  ncludes user's p
00000250: 7269 7661 7465 2062 696e 2069 6620 6974  rivate bin if it
00000260: 2065 7869 7374 730a 6966 205b 202d 6420   exists.if [ -d
00000270: 2224 484f 4d45 2f62 696e 2220 5d20 3b20  "$HOME/bin" ] ;
00000280: 7468 656e 0a20 2020 2050 4154 483d 2224  then.    PATH="$
00000290: 484f 4d45 2f62 696e 3a24 5041 5448 220a  HOME/bin:$PATH".
000002a0: 6669 0a0a 2320 7365 7420 5041 5448 2073  fi..# set PATH s
000002b0: 6f20 6974 2069 6e63 6c75 6465 7320 7573  o it includes us
000002c0: 6572 2773 2070 7269 7661 7465 2062 696e  er's private bin
000002d0: 2069 6620 6974 2065 7869 7374 730a 6966   if it exists.if
000002e0: 205b 202d 6420 2224 484f 4d45 2f2e 6c6f   [ -d "$HOME/.lo
000002f0: 6361 6c2f 6269 6e22 205d 203b 2074 6865  cal/bin" ] ; the
00000300: 6e0a 2020 2020 5041 5448 3d22 2448 4f4d  n.    PATH="$HOM
00000310: 452f 2e6c 6f63 616c 2f62 696e 3a24 5041  E/.local/bin:$PA
00000320: 5448 220a 6669 0a                        TH".fi.
bandit12@bandit:~$ xxd -help
Usage:
       xxd [options] [infile [outfile]]
    or
       xxd -r [-s [-]offset] [-c cols] [-ps] [infile [outfile]]
Options:
    -a          toggle autoskip: A single '*' replaces nul-lines. Default off.
    -b          binary digit dump (incompatible with -ps,-i,-r). Default hex.
    -C          capitalize variable names in C include file style (-i).
    -c cols     format <cols> octets per line. Default 16 (-i: 12, -ps: 30).
    -E          show characters in EBCDIC. Default ASCII.
    -e          little-endian dump (incompatible with -ps,-i,-r).
    -g bytes    number of octets per group in normal output. Default 2 (-e: 4).
    -h          print this summary.
    -i          output in C include file style.
    -l len      stop after <len> octets.
    -o off      add <off> to the displayed file position.
    -ps         output in postscript plain hexdump style.
    -r          reverse operation: convert (or patch) hexdump into binary.
    -r -s off   revert with <off> added to file positions found in hexdump.
    -d          show offset in decimal instead of hex.
    -s [+][-]seek  start at <seek> bytes abs. (or +: rel.) infile offset.
    -u          use upper case hex letters.
    -v          show version: "xxd 2021-10-22 by Juergen Weigert et al.".
bandit12@bandit:~$ xxd .profile -r
xxd: -r: Permission denied
bandit12@bandit:~$ xxd -r data.txt
�h44�z��A����@=�h4hh�␦␦␦��hd����������������9���1����������;,�
�����2�3d*58�~  �S�ZP^��luY��Br$�FP!%�s��h�?�)[=�h��O(B��2A���)�tZc��:�pã)�A�ˈ�0���΅A�yjeϢx,�(����z�E�+"�2�/�-��e"���^����t�j���$�d�@�dJơ'7\���$��m1c��#>�aԽ�EV��F��OCӐc@M�C���]��Y2^h8���D=��~        O�I��NDpF�+�|b#Jv�#�J��d�LފW$�Û�͖y�`
                                                                                                                    �\&��[�@*w�M�0θ��nr��C��`e$b�
                         ~�{���
                               ��`�<����a��?e:T���e�T4±b����)�@ِ���x=bandit12@bandit:~$ xxd -r data.txt | file -
/dev/stdin: gzip compressed data, was "data2.bin", last modified: Thu Oct  5 06:19:20 2023, max compression, from Unix
bandit12@bandit:~$ xxd -r data.txt > datos
-bash: datos: Permission denied
bandit12@bandit:~$ mkdir /tmp/42102028
bandit12@bandit:~$ cd /tmp/42102028
bandit12@bandit:/tmp/42102028$ xdd -r ~/data.txt > data
Command 'xdd' not found, did you mean:
  command 'pdd' from deb pdd (1.5-1)
  command 'xdu' from deb xdu (3.0-20)
  command 'xdo' from deb xdo (0.5.7-1)
  command 'ddd' from deb ddd (1:3.3.12-5.3build1)
  command 'xwd' from deb x11-apps (7.7+8build2)
  command 'xdx' from deb xdx (2.5.0-4)
  command 'xxd' from deb xxd (2:8.2.3995-1ubuntu2.11)
  command 'xfd' from deb x11-utils (7.7+5build2)
  command 'xd' from deb xd (3.29.02-1)
  command 'ldd' from deb libc-bin (2.35-0ubuntu3.4)
  command 'xdm' from deb xdm (1:1.1.11-3ubuntu2)
  command 'dd' from deb coreutils (8.32-4.1ubuntu1)
  command 'tdd' from deb devtodo (0.1.20+git20200830.0ad52b0-1)
  command 'xsd' from deb mono-devel (6.8.0.105+dfsg-3.2)
Try: apt install <deb name>
bandit12@bandit:/tmp/42102028$ xxd -r ~/data.txt >
-bash: syntax error near unexpected token `newline'
bandit12@bandit:/tmp/42102028$ xxd -r ~/data.txt > data
bandit12@bandit:/tmp/42102028$ ls
data
bandit12@bandit:/tmp/42102028$ file data
data: gzip compressed data, was "data2.bin", last modified: Thu Oct  5 06:19:20 2023, max compression, from Unix, original size modulo 2^32 573
bandit12@bandit:/tmp/42102028$ mv data data.gz
bandit12@bandit:/tmp/42102028$ ls
data.gz
bandit12@bandit:/tmp/42102028$ gzip -d data.gz
bandit12@bandit:/tmp/42102028$ ls
data
bandit12@bandit:/tmp/42102028$ file data
data: bzip2 compressed data, block size = 900k
bandit12@bandit:/tmp/42102028$ mv data data.bz2
bandit12@bandit:/tmp/42102028$ ls
data.bz2
bandit12@bandit:/tmp/42102028$ bzip2 -b data.bz2
bzip2: Bad flag `-b'
bzip2, a block-sorting file compressor.  Version 1.0.8, 13-Jul-2019.

   usage: bzip2 [flags and input files in any order]

   -h --help           print this message
   -d --decompress     force decompression
   -z --compress       force compression
   -k --keep           keep (don't delete) input files
   -f --force          overwrite existing output files
   -t --test           test compressed file integrity
   -c --stdout         output to standard out
   -q --quiet          suppress noncritical error messages
   -v --verbose        be verbose (a 2nd -v gives more)
   -L --license        display software version & license
   -V --version        display software version & license
   -s --small          use less memory (at most 2500k)
   -1 .. -9            set block size to 100k .. 900k
   --fast              alias for -1
   --best              alias for -9

   If invoked as `bzip2', default action is to compress.
              as `bunzip2',  default action is to decompress.
              as `bzcat', default action is to decompress to stdout.

   If no file names are given, bzip2 compresses or decompresses
   from standard input to standard output.  You can combine
   short flags, so `-v -4' means the same as -v4 or -4v, &c.

bandit12@bandit:/tmp/42102028$ bzip2 -d data.bz2
bandit12@bandit:/tmp/42102028$ ls
data
bandit12@bandit:/tmp/42102028$ dile data
Command 'dile' not found, did you mean:
  command 'dice' from snap dice (1.0.9)
  command 'dive' from snap dive (0.10.0)
  command 'file' from deb file (1:5.41-3ubuntu0.1)
  command 'zile' from deb zile (2.6.2-2)
  command 'kile' from deb kile (4:2.9.93-2)
  command 'vile' from deb vile (9.8v-1build1)
  command 'idle' from deb idle (3.10.6-1~22.04)
See 'snap info <snapname>' for additional versions.
bandit12@bandit:/tmp/42102028$ file data
data: gzip compressed data, was "data4.bin", last modified: Thu Oct  5 06:19:20 2023, max compression, from Unix, original size modulo 2^32 20480
bandit12@bandit:/tmp/42102028$ mv data data.gz
bandit12@bandit:/tmp/42102028$ gzip -d data.gz
bandit12@bandit:/tmp/42102028$ ls
data
bandit12@bandit:/tmp/42102028$ file data
data: POSIX tar archive (GNU)
bandit12@bandit:/tmp/42102028$ tar -d data.tar
tar: Refusing to read archive contents from terminal (missing -f option?)
tar: Error is not recoverable: exiting now
bandit12@bandit:/tmp/42102028$ mv data data.tar
bandit12@bandit:/tmp/42102028$ ls
data.tar
bandit12@bandit:/tmp/42102028$ tar -d data.tar
tar: Refusing to read archive contents from terminal (missing -f option?)
tar: Error is not recoverable: exiting now
bandit12@bandit:/tmp/42102028$ tar xf data.tar
bandit12@bandit:/tmp/42102028$ ls
data5.bin  data.tar
bandit12@bandit:/tmp/42102028$ rm data.tar
bandit12@bandit:/tmp/42102028$ file data.5bin
data.5bin: cannot open `data.5bin' (No such file or directory)
bandit12@bandit:/tmp/42102028$ ls
data5.bin
bandit12@bandit:/tmp/42102028$ mv data5.bin data5.tar
bandit12@bandit:/tmp/42102028$ tar xf data5.tar
bandit12@bandit:/tmp/42102028$ ls
data5.tar  data6.bin
bandit12@bandit:/tmp/42102028$ rm data5.tar
bandit12@bandit:/tmp/42102028$ mv data6.bin data6.bz2
bandit12@bandit:/tmp/42102028$ ls
data6.bz2
bandit12@bandit:/tmp/42102028$ bzip2 -b data6.bz2
bzip2: Bad flag `-b'
bzip2, a block-sorting file compressor.  Version 1.0.8, 13-Jul-2019.

   usage: bzip2 [flags and input files in any order]

   -h --help           print this message
   -d --decompress     force decompression
   -z --compress       force compression
   -k --keep           keep (don't delete) input files
   -f --force          overwrite existing output files
   -t --test           test compressed file integrity
   -c --stdout         output to standard out
   -q --quiet          suppress noncritical error messages
   -v --verbose        be verbose (a 2nd -v gives more)
   -L --license        display software version & license
   -V --version        display software version & license
   -s --small          use less memory (at most 2500k)
   -1 .. -9            set block size to 100k .. 900k
   --fast              alias for -1
   --best              alias for -9

   If invoked as `bzip2', default action is to compress.
              as `bunzip2',  default action is to decompress.
              as `bzcat', default action is to decompress to stdout.

   If no file names are given, bzip2 compresses or decompresses
   from standard input to standard output.  You can combine
   short flags, so `-v -4' means the same as -v4 or -4v, &c.

bandit12@bandit:/tmp/42102028$ bzip2 -b data6.bz2
bzip2: Bad flag `-b'
bzip2, a block-sorting file compressor.  Version 1.0.8, 13-Jul-2019.

   usage: bzip2 [flags and input files in any order]

   -h --help           print this message
   -d --decompress     force decompression
   -z --compress       force compression
   -k --keep           keep (don't delete) input files
   -f --force          overwrite existing output files
   -t --test           test compressed file integrity
   -c --stdout         output to standard out
   -q --quiet          suppress noncritical error messages
   -v --verbose        be verbose (a 2nd -v gives more)
   -L --license        display software version & license
   -V --version        display software version & license
   -s --small          use less memory (at most 2500k)
   -1 .. -9            set block size to 100k .. 900k
   --fast              alias for -1
   --best              alias for -9

   If invoked as `bzip2', default action is to compress.
              as `bunzip2',  default action is to decompress.
              as `bzcat', default action is to decompress to stdout.

   If no file names are given, bzip2 compresses or decompresses
   from standard input to standard output.  You can combine
   short flags, so `-v -4' means the same as -v4 or -4v, &c.

bandit12@bandit:/tmp/42102028$ bzip2 -d data6.bz2
bandit12@bandit:/tmp/42102028$ ls
data6
bandit12@bandit:/tmp/42102028$ file data6
data6: POSIX tar archive (GNU)
bandit12@bandit:/tmp/42102028$ mv data6 data6.tar
bandit12@bandit:/tmp/42102028$ ls
data6.tar
bandit12@bandit:/tmp/42102028$ tar xf data6.tar
bandit12@bandit:/tmp/42102028$ ls
data6.tar  data8.bin
bandit12@bandit:/tmp/42102028$ rm data6.tar
bandit12@bandit:/tmp/42102028$ file data8.bin
data8.bin: gzip compressed data, was "data9.bin", last modified: Thu Oct  5 06:19:20 2023, max compression, from Unix, original size modulo 2^32 49
bandit12@bandit:/tmp/42102028$ mv data8.bin data8.gz
bandit12@bandit:/tmp/42102028$ gzip -d data8.gz
bandit12@bandit:/tmp/42102028$ ls
data8
bandit12@bandit:/tmp/42102028$ file data8
data8: ASCII text
bandit12@bandit:/tmp/42102028$ cat data8
The password is wbWdlBxEir4CaE8LaPhauuOo6pwRmrDw
bandit12@bandit:/tmp/42102028$

```

```
bandit12@bandit:~$ xxd -r data.txt | zcat | bzcat | zcat | tar xO | tar xO | bzcat | tar xO | zcat
The password is wbWdlBxEir4CaE8LaPhauuOo6pwRmrDw
bandit12@bandit:~$
```
# Notas adicionales

# Referencias

[Hex dump - Wikipedia](https://en.wikipedia.org/wiki/Hex_dump)