# Module 5: File Globbing
In this module we learn about *globs* which can be interpreted as kind of short forms for file paths.
Before executing commands that you enter, the shell first performs expansions on them, and one of these expansions is globbing.

### Challenge 1: Matching with *
Here, we learn about the first glob, ie, ~ * ~. 
The shell treats it as a wildcard and tries to replace the argument with any files that match the pattern.
We should note that ` * ` matches any part of the filename except for __'/'__ or a leading __'.'__ character.

```
hacker@globbing~matching-with-:~$ cd /ch*
hacker@globbing~matching-with-:/challenge$ /challenge/run
You ran me with the working directory of /challenge! Here is your flag:
pwn.college{oND-4SOnnXD0EYDd0mgF4NRAs4t.dFjM4QDL1IzN0czW}

```

### Challenge 2: Matching with ?
Here, we learn about the second glob, ie, ~ ? ~.
the shell will treat it as single-character wildcard. 
This works like ` * `, but only matches one character.

```
hacker@globbing~matching-with-:~$ cd /?ha??enge
hacker@globbing~matching-with-:/challenge$ /challenge/run
You ran me with the working directory of /challenge! Here is your flag:
pwn.college{seC6fdbux3XOWnGLrZGLbwiMrZj.dJjM4QDL1IzN0czW}

```

### Challenge 3: Matching with []
Here, we learn about the next glob, ie, ~ [] ~.
The square brackes are, essentially, a limited form of ? 
In that instead of matching any character, [] is a wildcard for some subset of potential characters, specified within the brackets.
In this challenge, we need to change our working directory to `/challenge/files` and run `/challenge/run` with a single argument that globs into 3 other files

```
hacker@globbing~matching-with-:~$ cd /challenge/files
hacker@globbing~matching-with-:/challenge/files$ /challenge/run file_[absh]
You got it! Here is your flag!
pwn.college{0zu6ZXu97WXKhUVYBwlhROaoY92.dNjM4QDL1IzN0czW}

```

### Challenge 4: Matching paths with []
This challenge is similar to the previous challenge, however, here we need to file glob the absolute path.

```
hacker@globbing~matching-paths-with-:~$ /challenge/run /challenge/files/file_[bash]
You got it! Here is your flag!
pwn.college{0_D9jB6N7jt0Khmq7e-s0jq-zhn.dRjM4QDL1IzN0czW}

```

### Challenge 5: Mixing globs.
This challegne is a combination of all the previous challenges in this module. Here we need to __cd__ to `/challenge/files`.
Further we need to use our prior learned knowledge to match 3 given files using 6 chars or less.

```
hacker@globbing~mixing-globs:~$ cd /challenge/files
hacker@globbing~mixing-globs:/challenge/files$ /challenge/run [cep]*
You got it! Here is your flag!
pwn.college{Umx2HOzepZmmPCyKmGOMrw3iVoh.dVjM4QDL1IzN0czW}

```

### Challenge 6: Exclusionary Globbing 
Here, we are introduced to ~ ! ~ and ` ^ ` commands within the ` [] ` glob. 
They work as inversions, that is exclude search for all characters mentioned within the brackets.
This challenge is also a combination of the previous challenges.

```
hacker@globbing~exclusionary-globbing:~$ cd /challenge/files
hacker@globbing~exclusionary-globbing:/challenge/files$ /challenge/run [!pwn]*
You got it! Here is your flag!
pwn.college{s0UGVOWMuvUR0I2me-QbDYvkc39.dZjM4QDL1IzN0czW}

```
