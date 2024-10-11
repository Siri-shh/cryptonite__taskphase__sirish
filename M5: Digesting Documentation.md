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

### Challenge 4: Searching Manuals
This challenge is similar to the previous chalenge but some extra commands and arfuments have been added to retriove the flag.
```
hacker@man~searching-for-manuals:~$ man -K /challenge/challenge

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

       --culbdj NUM
              print the flag if NUM is 500

AUTHOR
       Written by Zardus.

REPORTING BUGS
       The  repository  for  this  dojo:  <https://github.com/pwncol‐
       lege/linux-luminarium/>

SEE ALSO
       man(1) bash-builtins(7)

pwn.college                    May 2024                  CHALLENGE(1)
hacker@man~searching-for-manuals:~$ /challenge/challenge --culbdj 500
Correct usage! Your flag: pwn.college{cJulb5dBBEjKJqYE00npQIKPDdH.dZTM4QDL1IzN0czW}

```

### Challenge 5: Sarching for manuals
In this chanllenge, the `man` page for *__challenge__* is hidden by changing its name to a randomized name. To locate this random name, we need to read the manual of the man page via `man man`.

```

```

### Challenge 6: Sarching for manuals
In this chanllenge, we discover the `--help` argument. It is used when a program doesnt have a *man* page.
```

hacker@man~helpful-programs:~$ /challenge/challenge --help
usage: a challenge to make you ask for help [-h] [--fortune] [-v]
                                            [-g GIVE_THE_FLAG] [-p]

optional arguments:
  -h, --help            show this help message and exit
  --fortune             read your fortune
  -v, --version         get the version number
  -g GIVE_THE_FLAG, --give-the-flag GIVE_THE_FLAG
                        get the flag, if given the correct value
  -p, --print-value     print the value that will cause the -g option
                        to give you the flag
hacker@man~helpful-programs:~$ /challenge/challenge -p
The secret value is: 940
hacker@man~helpful-programs:~$ /challenge/challenge -g 940
Correct usage! Your flag: pwn.college{w9FwobM4xFu0eR0G2vncu8U39zm.ddjM4QDL1IzN0czW}
```

### Challenge 7: Help for Builtins
Here, we are introduced to builtins. Builtins are invoked just like commands, but the shell handles them internally instead of launching other programs. 
In this challenge, ~challenge` is designed as a shell builtin command, therefore we need to look it up with appropriate methods to figure out the secret value to pass it amd obtain the flag.

```
hacker@man~help-for-builtins:~$ help challenge
challenge: challenge [--fortune] [--version] [--secret SECRET]
    This builtin command will read you the flag, given the right arguments!

    Options:
      --fortune         display a fortune
      --version         display the version
      --secret VALUE    prints the flag, if VALUE is correct

    You must be sure to provide the right value to --secret. That value
    is "8wDlGOjf".
hacker@man~help-for-builtins:~$ challenge --secret 8wDlGOjf
Correct! Here is your flag!
pwn.college{8wDlGOjfAinNgPGD6uUVG3FJjJx.dRTM5QDL1IzN0czW}.

```
