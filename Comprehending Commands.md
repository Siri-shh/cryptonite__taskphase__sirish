# Module 3: Comprehending Commands
### Challenge 1: cat: not the pet, but the command!
Here, we learn about the `cat` command. It reads out files, and concatenate multiple files if provided multiple arguments.
In this challenge, we need to simply print the __flag__ file.
```
hacker@commands~cat-not-the-pet-but-the-command:~$ cat flag
pwn.college{gskdQ30ib6wg4OX0DcY2AAa_Y4M.dFzN1QDL1IzN0czW}
```

### Challenge 2: catting absolute paths.
Here we need to `cat` the __flag__ file from its absolute path.
```
hacker@commands~catting-absolute-paths:~$ cat /flag
pwn.college{sXyUVKP8PKNzu-pMq3Xm3pXjMhK.dlTM5QDL1IzN0czW}
```

### Challenge 3: more catting practice.
Here we need to retrieve the __flag__ file from its absolute path.
```
You cannot use the 'cd' command in this level, and must retrieve the flag by
absolute path. Plus, I hid the flag in a different directory! You can find it
in the file /lib/gold-ld/flag. Go cat it out **without** cding into that
directory!
hacker@commands~more-catting-practice:~$ cat /lib/gold-ld/flag
pwn.college{0paLcBUMRFe6_WgmnT9HUCRGC7j.dBjM5QDL1IzN0czW}
```

### Challenge 4: grepping for a needle in a haystack.
We learn about the `grep` command that searches for a string or lines of text in a challenge.
```
hacker@commands~grepping-for-a-needle-in-a-haystack:~$ grep pwn.college /challenge/data.txt
pwn.college{omCiN7ENxcQU1A1bFuDSpcwsE7J.ddTM4QDL1IzN0czW}
```

### Challenge 5: listing files.
We learn about the `ls` command that lists all the files in the directory or path in argument.
```
hacker@commands~listing-files:~$ ls /challenge
29216-renamed-run-17752  DESCRIPTION.md
hacker@commands~listing-files:~$ /challenge/29216-renamed-run-17752
Yahaha, you found me! Here is your flag:
pwn.college{ggvJOEovcYPniZjt9CtTwH4tbdU.dhjM4QDL1IzN0czW}
```

### Challenge 6: touch files.
We learn about the `touch` command that creates a blank new file in the directory or path in argument.
```
hacker@commands~touching-files:~$ touch /tmp/pwn
hacker@commands~touching-files:~$ touch /tmp/college
hacker@commands~touching-files:~$ /challenge/run
Success! Here is your flag:
pwn.college{cwn9ZLyB-fjzZ25mfJKHbQQn2kS.dBzM4QDL1IzN0czW}

```

### Challenge 7: removing files.
We learn about the `rm` command that removes files in the argument.
```
hacker@commands~removing-files:~$ ls
Desktop  a  delete_me
hacker@commands~removing-files:~$ rm delete_me
hacker@commands~removing-files:~$ /challenge/check
Excellent removal. Here is your reward:
pwn.college{Qsh1VulzcRSQDaqRwS8KgM5y8ZQ.dZTOwUDL1IzN0czW}

```

### Challenge 8: hidden files.
We learn about the `ls` command, used with the `-a` flag which lists all the hidden files as well.
```
hacker@commands~hidden-files:~$ cd /
hacker@commands~hidden-files:/$ ls -a
.                      bin        etc    lib64   nix   run   tmp
..                     boot       home   libx32  opt   sbin  usr
.dockerenv             challenge  lib    media   proc  srv   var
.flag-187082556810175  dev        lib32  mnt     root  sys
hacker@commands~hidden-files:/$ cat .flag-187082556810175
pwn.college{QGeUJoZSx9bkB7LCYrBUfkJo2Ae.dBTN4QDL1IzN0czW}

```

### Challenge 9: an epic filesystem quest.
We use the `cd, ls, cat` commands, more extensively.
The challenge follows a step of guidelines and instructuins to be followed.
> Your first clue is in /. Head on over there.
> ```
> hacker@commands~an-epic-filesystem-quest:~$ cd /
> ```
> Look around with ls. There'll be a file named HINT or CLUE or something along those lines!
> ```
> hacker@commands~an-epic-filesystem-quest:/$ ls
> CLUE  challenge  flag  lib32   media  opt   run   sys  var
> bin   dev        home  lib64   mnt    proc  sbin  tmp
> boot  etc        lib   libx32  nix    root  srv   usr
>```
> 

> cat that file to read the clue!
>```
> hacker@commands~an-epic-filesystem-quest:/$ cat CLUE
>Lucky listing!
>The next clue is in: /usr/share/icons/hicolor/256x256
>```
> Depending on what the clue says, head on over to the next directory (or don't!).
> Follow the clues to the flag!
```
hacker@commands~an-epic-filesystem-quest:/usr/share/icons/hicolor/256x256$ cat NUGGET
Great sleuthing!
The next clue is in: /usr/local/lib/python3.8/dist-packages/setuptools/_vendor/importlib_resources/tests/__pycache__

Watch out! The next clue is **trapped**. You'll need to read it out without 'cd'ing into the directory; otherwise, the clue will self destruct!
hacker@commands~an-epic-filesystem-quest:/usr/share/icons/hicolor/256x256$lls /usr/local/lib/python3.8/dist-packages/setuptools/_vendor/importlib_resources/tests/__pycache__
DISPATCH-TRAPPED                        test_open.cpython-38.pyc
__init__.cpython-38.pyc                 test_path.cpython-38.pyc
_path.cpython-38.pyc                    test_read.cpython-38.pyc
test_compatibilty_files.cpython-38.pyc  test_reader.cpython-38.pyc
test_contents.cpython-38.pyc            test_resource.cpython-38.pyc
test_custom.cpython-38.pyc              util.cpython-38.pyc
test_files.cpython-38.pyc               zip.cpython-38.pyc
test_functional.cpython-38.pyc
hacker@commands~an-epic-filesystem-quest:/usr/share/icons/hicolor/256x256$cc
at /usr/local/lib/python3.8/dist-packages/setuptools/_vendor/importlib_resources/tests/__pycache__/DISPATCH-TRAPPED
Tubular find!
The next clue is in: /usr/share/doc/libsepol1-dev

The next clue is **delayed** --- it will not become readable until you enter the directory with 'cd'.
hacker@commands~an-epic-filesystem-quest:/usr/share/icons/hicolor/256x256$cc
d /usr/share/doc/libsepol1-dev
hacker@commands~an-epic-filesystem-quest:/usr/share/doc/libsepol1-dev$ ls
TEASER  changelog.Debian.gz  copyright
hacker@commands~an-epic-filesystem-quest:/usr/share/doc/libsepol1-dev$ cat T
EASER
Lucky listing!
The next clue is in: /usr/local/lib/python3.8/dist-packages/jedi/third_party/typeshed/stdlib/2/multiprocessing/dummy

The next clue is **hidden** --- its filename starts with a '.' character. You'll need to look for it using special options to 'ls'.
hacker@commands~an-epic-filesystem-quest:/usr/share/doc/libsepol1-dev$ cd /usr/local/lib/python3.8/dist-packages/jedi/third_party/typeshed/stdlib/2/multiprocessing/dummy
hacker@commands~an-epic-filesystem-quest:/usr/local/lib/python3.8/dist-packages/jedi/third_party/typeshed/stdlib/2/multiprocessing/dummy$ ls -a
.  ..  .POINTER  __init__.pyi  connection.pyi
hacker@commands~an-epic-filesystem-quest:/usr/local/lib/python3.8/dist-packages/jedi/third_party/typeshed/stdlib/2/multiprocessing/dummy$ cat .POINTER
Tubular find!
The next clue is in: /usr/local/lib/python3.8/dist-packages/jedi/third_party/django-stubs/django-stubs/views/decorators

The next clue is **delayed** --- it will not become readable until you enter the directory with 'cd'.
hacker@commands~an-epic-filesystem-quest:/usr/local/lib/python3.8/dist-packages/jedi/third_party/typeshed/stdlib/2/multiprocessing/dummy$ cd /usr/local/lib/python3.8/dist-packages/jedi/third_party/django-stubs/django-stubs/views/decorators
hacker@commands~an-epic-filesystem-quest:/usr/local/lib/python3.8/dist-packages/jedi/third_party/django-stubs/django-stubs/views/decorators$ ls
BLUEPRINT     cache.pyi         csrf.pyi   gzip.pyi  vary.pyi
__init__.pyi  clickjacking.pyi  debug.pyi  http.pyi
hacker@commands~an-epic-filesystem-quest:/usr/local/lib/python3.8/dist-packages/jedi/third_party/django-stubs/django-stubs/views/decorators$ cat BLUEPRINT
Yahaha, you found me!
The next clue is in: /usr/share/man/sl/man8
hacker@commands~an-epic-filesystem-quest:/usr/local/lib/python3.8/dist-packages/jedi/third_party/django-stubs/django-stubs/views/decorators$ cd /usr/share/man/sl/man8
hacker@commands~an-epic-filesystem-quest:/usr/share/man/sl/man8$ ls
EVIDENCE        installkernel.8.gz  run-parts.8.gz
add-shell.8.gz  remove-shell.8.gz   savelog.8.gz
hacker@commands~an-epic-filesystem-quest:/usr/share/man/sl/man8$ cat EVIDENC
E
Tubular find!
The next clue is in: /usr/share/racket/pkgs/plot-lib/plot/private/common/compiled

Watch out! The next clue is **trapped**. You'll need to read it out without 'cd'ing into the directory; otherwise, the clue will self destruct!
hacker@commands~an-epic-filesystem-quest:/usr/share/man/sl/man8$ ls /usr/share/racket/pkgs/plot-lib/plot/private/common/compiled
ALERT-TRAPPED                math_rkt.dep
axis-transform_rkt.dep       math_rkt.zo
axis-transform_rkt.zo        nonrenderer_rkt.dep
contract_rkt.dep             nonrenderer_rkt.zo
contract_rkt.zo              parameter-group_rkt.dep
currency_rkt.dep             parameter-group_rkt.zo
currency_rkt.zo              parameter-groups_rkt.dep
date-time_rkt.dep            parameter-groups_rkt.zo
date-time_rkt.zo             parameters_rkt.dep
deprecation-warning_rkt.dep  parameters_rkt.zo
deprecation-warning_rkt.zo   plot-device_rkt.dep
draw-attribs_rkt.dep         plot-device_rkt.zo
draw-attribs_rkt.zo          plot-element_rkt.dep
draw_rkt.dep                 plot-element_rkt.zo
draw_rkt.zo                  sample_rkt.dep
file-type_rkt.dep            sample_rkt.zo
file-type_rkt.zo             samplers_rkt.dep
format_rkt.dep               samplers_rkt.zo
format_rkt.zo                ticks_rkt.dep
kde_rkt.dep                  ticks_rkt.zo
kde_rkt.zo                   type-doc_rkt.dep
leftover-contracts_rkt.dep   type-doc_rkt.zo
leftover-contracts_rkt.zo    typed-srfi19_rkt.dep
legend_rkt.dep               typed-srfi19_rkt.zo
legend_rkt.zo                types_rkt.dep
marching-cubes_rkt.dep       types_rkt.zo
marching-cubes_rkt.zo        untyped-utils_rkt.dep
marching-squares_rkt.dep     untyped-utils_rkt.zo
marching-squares_rkt.zo      utils_rkt.dep
marching-utils_rkt.dep       utils_rkt.zo
marching-utils_rkt.zo
hacker@commands~an-epic-filesystem-quest:/usr/share/man/sl/man8$ cat /usr/share/racket/pkgs/plot-lib/plot/private/common/compiled/ALERT-TRAPPED
Congratulations, you found the clue!
The next clue is in: /usr/share/javascript/mathjax/unpacked/jax/output/HTML-CSS/fonts/STIX-Web/Main
hacker@commands~an-epic-filesystem-quest:/usr/share/man/sl/man8$ cd /usr/share/javascript/mathjax/unpacked/jax/output/HTML-CSS/fonts/STIX-Web/Main
hacker@commands~an-epic-filesystem-quest:/usr/share/javascript/mathjax/unpacked/jax/output/HTML-CSS/fonts/STIX-Web/Main$ ls
Bold  BoldItalic  Italic  Regular  SPOILER
hacker@commands~an-epic-filesystem-quest:/usr/share/javascript/mathjax/unpacked/jax/output/HTML-CSS/fonts/STIX-Web/Main$ cat SPOILER
CONGRATULATIONS! Your perserverence has paid off, and you have found the flag!
It is: pwn.college{cCNKOaFrE5aCBqJVgSNqotOKeg0.dljM4QDL1IzN0czW}

```

### challenge 10: making directories
We learn about the `mkdir` command which creates a new directory in the location specified (or the cwd, by default).
```
hacker@commands~making-directories:~$ mkdir /tmp/pwn
hacker@commands~making-directories:~$ cd /tmp/pwn
hacker@commands~making-directories:/tmp/pwn$ touch college
hacker@commands~making-directories:/tmp/pwn$ /challenge/run
Success! Here is your flag:
pwn.college{AqW-R-hFRKZtP5_KIi4tWiJ5zSX.dFzM4QDL1IzN0czW}
```

### challenge 11: finding files
We learn about the `find` command searches matches in the current working directory, or in the location specified.
```
hacker@commands~finding-files:~$ find / -name flag
find: ‘/tmp/tmp.MiOQGWw5Zc’: Permission denied
find: ‘/etc/ssl/private’: Permission denied
/usr/local/lib/python3.8/dist-packages/pwnlib/flag
/usr/local/share/radare2/5.9.5/flag
/usr/share/javascript/mathjax/jax/output/HTML-CSS/fonts/Asana-Math/DoubleStruck/flag
find: ‘/run/mysqld’: Permission denied
find: ‘/run/sudo’: Permission denied
find: ‘/root’: Permission denied
/opt/pwndbg/.venv/lib/python3.8/site-packages/pwnlib/flag
/opt/radare2/libr/flag
find: ‘/proc/tty/driver’: Permission denied
find: ‘/proc/7/fd’: Permission denied
find: ‘/proc/7/map_files’: Permission denied
find: ‘/proc/7/fdinfo’: Permission denied
find: ‘/proc/7/ns’: Permission denied
/nix/store/1yagn5s8sf7kcs2hkccgf8d0wxlrv5sz-radare2-5.9.0/share/radare2/5.9.0/flag
/nix/store/pmvk2bk4p550w182rjfm529kfqddnvh3-python3.11-pwntools-4.12.0/lib/python3.11/site-packages/pwnlib/flag
hacker@commands~finding-files:~$ ls /usr/share/javascript/mathjax/jax/output/HTML-CSS/fonts/Asana-Math/DoubleStruck/flag
/usr/share/javascript/mathjax/jax/output/HTML-CSS/fonts/Asana-Math/DoubleStruck/flag
hacker@commands~finding-files:~$ cat /usr/share/javascript/mathjax/jax/output/HTML-CSS/fonts/Asana-Math/DoubleStruck/flag
pwn.college{wSm4uo4Yn77p_S9L2oFd9ZFDT7B.dJzM4QDL1IzN0czW}
```

## challenge 12: Linking files
We learn about the `ln` command with a `-s` argument used to create symbolic links

```
hacker@commands~linking-files:~$ /challenge/catflag
About to read out the /home/hacker/not-the-flag file!
cat: /home/hacker/not-the-flag: No such file or directory
hacker@commands~linking-files:~$ ln -s /flag ~/not-the-flag
hacker@commands~linking-files:~$ /challenge/catflag
About to read out the /home/hacker/not-the-flag file!
pwn.college{oVZfPATM5wzK3vyk7bxGcA8pJ6b.dlTM1UDL2EjN0czW}

```
