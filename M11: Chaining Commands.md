# Module 11: Chaining Commands

### Challenge 1: Chanining with semicolons

```
hacker@chaining~chaining-with-semicolons:~$ /challenge/pwn; /challenge/college
Yes! You chained /challenge/pwn and /challenge/college! Here is your flag:
pwn.college{MLCu5N0v9_nLWlFcPJbtDXNU1nT.dVTN4QDL1IzN0czW}

```

### Challenge 2: Your first Shell Script

```
hacker@chaining~your-first-shell-script:~$ echo /challenge/pwn > x.sh
hacker@chaining~your-first-shell-script:~$ echo /challenge/college >> x.sh
hacker@chaining~your-first-shell-script:~$ bash x.sh
Great job, you've written your first shell script! Here is the flag:
pwn.college{crGIfBHWvZJjGxYyIObbg9a853L.dFzN4QDL1IzN0czW}

```

### Challenge 3: Redirecting Script Output
```
hacker@chaining~redirecting-script-output:~$ echo /challenge/pwn > x.sh
hacker@chaining~redirecting-script-output:~$ echo /challenge/college >> x.sh
hacker@chaining~redirecting-script-output:~$ bash x.sh | /challenge/solve
Correct! Here is your flag:
pwn.college{w5Sx2iAyfbchtoSrcgRcp5Lva1E.dhTM5QDL1IzN0czW}

```

### Challenge 4: Executable Shell Scripts

```
hacker@chaining~executable-shell-scripts:~$ echo /challenge/solve > ~/x.sh
hacker@chaining~executable-shell-scripts:~$ chmod uog+wrx ~/x.sh
hacker@chaining~executable-shell-scripts:~$ ./x.sh
Congratulations on your shell script execution! Your flag:
pwn.college{ctMxUzrltcJPbUf7YDTHzHRZ6pe.dRzNyUDL1IzN0czW}

```
