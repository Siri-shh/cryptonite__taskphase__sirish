# Module 2: Pondering Paths
### Challenge 1: The Root
Here, we need to invoke a program **pwn** from the root directory **'/ '**
```
hacker@paths~the-root:~$ /pwn
BOOM!!!
Here is your flag:
pwn.college{IWc9Gn2cJhsxhfWBEKO4mF_MSE-.dhzN5QDL1IzN0czW}
```

### Challenge 2: Program and absolute paths
Here, the flag is placed in the __challenge__ directory which, in turn, is located in the root directory **/**
The name of the program is **run**.
To get the flag, we need to invoke this program directly, ie, form it's absolute path
```
hacker@paths~program-and-absolute-paths:~$ /challenge/run
Correct!!!
/challenge/run is an absolute path! Here is your flag:
pwn.college{YBgh-HmG1HcUS1G9aTNplKnoLfe.dVDN1QDL1IzN0czW}
```

### Challenge 3: Position thy self
Here, we learn about the **cd**(change directory) command. 
It requires adding an argument beside it to change the __current working directory__
The challenge requires us to execute the `/challenge/run` program from a specific path.
```
hacker@paths~position-thy-self:~$ /challenge/run
Incorrect...
You are not currently in the /usr/include directory.
Please use the `cd` utility to change directory appropriately.
hacker@paths~position-thy-self:~$ cd /usr/include
hacker@paths~position-thy-self:/usr/include$ /challenge/run
Correct!!!
/challenge/run is an absolute path, invoked from the right directory!
Here is your flag:
pwn.college{Eow_EGiS_ydniiTTCsJguNxqSoI.dZDN1QDL1IzN0czW}

```

### Challenge 4: Position elsewhere
This challenge is identical to the previous one.
The challenge requires us to execute the `/challenge/run` program from another specific path.
```
hacker@paths~position-elsewhere:~$ /challenge/run
Incorrect...
You are not currently in the /usr/bin directory.
Please use the `cd` utility to change directory appropriately.
hacker@paths~position-elsewhere:~$ cd /usr/bin
hacker@paths~position-elsewhere:/usr/bin$ /challenge/run
Correct!!!
/challenge/run is an absolute path, invoked from the right directory!
Here is your flag:
pwn.college{o9IUwljxQksOdP1-0sWxQJiuda0.ddDN1QDL1IzN0czW}

```

### Challenge 5: Position yet elsewhere
This challenge is __yet again__ identical to the previous one.
The challenge requires us to execute the `/challenge/run` program from yet another specific path.
```
hacker@paths~position-yet-elsewhere:~$ /challenge/run
Incorrect...
You are not currently in the /var directory.
Please use the `cd` utility to change directory appropriately.
hacker@paths~position-yet-elsewhere:~$ cd /var
hacker@paths~position-yet-elsewhere:/var$ /challenge/run
Correct!!!
/challenge/run is an absolute path, invoked from the right directory!
Here is your flag:
pwn.college{AAkypIi60k24ZBjdihrH5HCmadD.dhDN1QDL1IzN0czW}
hacker@paths~position-yet-elsewhere:/var$

```

### Challenge 6: Implicit relative paths from /
Here, we learn the significant different of relative and absolute paths and how the two link
> the current working directory does matter for relative paths.
> * `A relative path` is any path that does not start at root (i.e., it does not start with /).
> * A `relative path` is interpreted relative to your current working directory (cwd).
> * Your `cwd` is the directory that your prompt is currently located at.

In this challenge we need to run `/challenge/run` using a relative path while having a current working directory of /.
So we need to __cd__ to **/** and then do accordingly.
```
hacker@paths~implicit-relative-paths-from-:~$ /challenge/run
Incorrect...
You are not currently in the / directory.
Please use the `cd` utility to change directory appropriately.
hacker@paths~implicit-relative-paths-from-:~$ cd /
hacker@paths~implicit-relative-paths-from-:/$ challenge/run
Correct!!!
challenge/run is a relative path, invoked from the right directory!
Here is your flag:
pwn.college{EinBT-Lo8xMiSf4EIM7MHZYgdV2.dlDN1QDL1IzN0czW}

```

### Challenge 7: Explicit relative paths from /
This challenge introduces us to the dot `.` which basically refers the the cwd.
The challenge requires us to execute the `/challenge/run` program from a specified path while also getting familiar with the `.` enttry
```
hacker@paths~explicit-relative-paths-from-:~$ cd /
hacker@paths~explicit-relative-paths-from-:/$ ./challenge/run
Correct!!!
./challenge/run is a relative path, invoked from the right directory!
Here is your flag:
pwn.college{Y9rQaKY12us4SomQgId7UGPZryz.dBTN1QDL1IzN0czW}

```
### Challenge 8: Implicit relative path
In this level, we start using the `.` entry even more and run it from the `/challenge` directory.
LINUX avoids the interpretation of a file/directory, entered as a naked path, ie, without a `/` as asafety measure.
The challenge requires us to execute the `run` program from inside the `challenge` directory.
```
hacker@paths~implicit-relative-path:~$ cd /challenge
hacker@paths~implicit-relative-path:/challenge$ ./run
Correct!!!
./run is a relative path, invoked from the right directory!
Here is your flag:
pwn.college{khSkVuH4XtT2ZTj0rgvrlgp-HMF.dFTN1QDL1IzN0czW}

```

### Challenge 9: Home Sweet Home
In this level, we learn about the home directory `/home/hacker` .
The `~` command refers to the home directory.
the expansion of `~` is an absolute path.
In this challenge, we need to run `/challenge/path` from the home directory, as an absolute path.
The major constraint is that the argument should be three characters or less, therefore, the `~` comes into play. 
```
hacker@paths~home-sweet-home:~$ /challenge/run ~/a
Writing the file to /home/hacker/a!
... and reading it back to you:
pwn.college{g0JcorOCbnWHgK9VRR94D0HRHNA.dNzM4QDL1IzN0czW}

```

