# Module 4: Digesting Documentation

### Challenge 1: Learning from Documentation.
We learn the appropriate use of __arguments__ while running the `/challenge/challenge` program.
```
hacker@man~learning-from-documentation:~$ /challenge/challenge --giveflag
Correct argument! Here is your flag:

```

### Challenge 2: Learning Complex Usage.
We learn about the commands that take arguments to their arguments, like *find* ie `find -name filename`
```
hacker@man~learning-complex-usage:~$ /challenge/challenge --printfile /flag
Correct argument! Here is the /flag file:
pwn.college{Mn_OnFhEHGpT6jnBXOZEq3HVDjG.dVjM5QDL1IzN0czW}

```

### Challenge 3: Reading Manuals.
We learn about the `man` command that displlays the manual of a command, if available.
```hacker@man~reading-manuals:~$ man challenge

CHALLENGE(1)              Challenge Commands             CHALLENGE(1)

NAME
       /challenge/challenge - print the flag!

SYNOPSIS
       challenge OPTION

DESCRIPTION
       Output the flag when called with the right arguments.

       --fortune
              read a fortune

       --version
              output version information and exit

       --zgidgu NUM
              print the flag if NUM is 000

AUTHOR
       Written by Zardus.

REPORTING BUGS
       The  repository  for  this  dojo:  <https://github.com/pwncol‐
       lege/linux-luminarium/>

SEE ALSO
       man(1) bash-builtins(7)

pwn.college                    May 2024                  CHALLENGE(1)
hacker@man~reading-manuals:~$ /challenge/challenge --zgidgu 000
Correct usage! Your flag: pwn.college{00zFgS0iL6CM35dOQYY6Qg4uGYa.dRTM4QDL1IzN0czW}

```
