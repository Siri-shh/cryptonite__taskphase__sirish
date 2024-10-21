# Module 10: Untangling Users

### Challenge 1: Benoming Root with su

```
hacker@users~becoming-root-with-su:~$ su
Password:
root@users~becoming-root-with-su:/home/hacker# cat /flag
pwn.college{Avw4v3tfmztJnFjlVSmRdd8UvQj.dVTN0UDL1IzN0czW}

```

### Challenge 2: Other users with su

```
hacker@users~becoming-root-with-su:~$ su
Password:
root@users~becoming-root-with-su:/home/hacker# cat /flag
pwn.college{Avw4v3tfmztJnFjlVSmRdd8UvQj.dVTN0UDL1IzN0czW}

```

### Challenge 3: Cracking Passwords

```
hacker@users~cracking-passwords:~$ cat /challenge/shadow-leak
root:*:19873:0:99999:7:::
daemon:*:19873:0:99999:7:::
bin:*:19873:0:99999:7:::
sys:*:19873:0:99999:7:::
sync:*:19873:0:99999:7:::
games:*:19873:0:99999:7:::
man:*:19873:0:99999:7:::
lp:*:19873:0:99999:7:::
mail:*:19873:0:99999:7:::
news:*:19873:0:99999:7:::
uucp:*:19873:0:99999:7:::
proxy:*:19873:0:99999:7:::
www-data:*:19873:0:99999:7:::
backup:*:19873:0:99999:7:::
list:*:19873:0:99999:7:::
irc:*:19873:0:99999:7:::
gnats:*:19873:0:99999:7:::
nobody:*:19873:0:99999:7:::
_apt:*:19873:0:99999:7:::
hacker::20000:0:99999:7:::
zardus:$6$pXUlUH.wbd299hx5$eWz1To7P8psmM55T9.Ds8SDK0sC.AWqAageE/iYs..B2lH2lJI0eXpvLSkCdxqUKCRky16RcpugiFYxf9TlEv.:20017:0:99999:7:::
hacker@users~cracking-passwords:~$ john /challenge/shadow-leak
Loaded 1 password hash (crypt, generic crypt(3) [?/64])
Press 'q' or Ctrl-C to abort, almost any other key for status
0g 0:00:00:03 35% 1/3 0g/s 243.8p/s 243.8c/s 243.8C/s zzardus99999..Ozardus
aardvark         (zardus)
1g 0:00:00:22 100% 2/3 0.04430g/s 257.9p/s 257.9c/s 257.9C/s Johnson..buzz
Use the "--show" option to display all of the cracked passwords reliably
Session completed
hacker@users~cracking-passwords:~$ su zardus
Password:
zardus@users~cracking-passwords:/home/hacker$ /challenge/run
Congratulations, you have become Zardus! Here is your flag:
pwn.college{QvHcu5AEPwrDU_ENXYRDs9bLq2K.ddTN0UDL1IzN0czW}

```

### Challenge 4: sing sudo

```
hacker@users~using-sudo:~$ sudo cat /flag
pwn.college{MFi9z0DGYwhETXrv0kmVgjcQh7m.dhTN0UDL1IzN0czW}

```

