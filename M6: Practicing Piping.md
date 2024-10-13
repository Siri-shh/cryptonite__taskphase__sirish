# Module 6: Practicing Piping
This module focuses on __*input - output redirection*__
LINUX has 3 standard channels of communication:
1. Standard __input__ : `stdin`
2. Standard __output__: `stdout`
3. Standard __errors__: `stderr`

### Challenge 1: Redirecting output
We learn about the ` > ` character. It redirects standard output to files. 

```
hacker@piping~redirecting-output:~$ echo PWN > COLLEGE
Correct! You successfully redirected 'PWN' to the file 'COLLEGE'! Here is your
flag:
pwn.college{MkNhZ1VL3LOr_UBZjHf_H1bzylG.dRjN1QDL1IzN0czW}

```

### Challenge 2: Redirecting more output
This challenge is an extension of the previous one. Here we learn that, commands other than ` echo` can also be redirected to files.

```
hacker@piping~redirecting-more-output:~$ /challenge/run > myflag
[INFO] WELCOME! This challenge makes the following asks of you:
[INFO] - the challenge will check that output is redirected to a specific file path : myflag
[INFO] - the challenge will output a reward file if all the tests pass : /flag
[HYPE] ONWARDS TO GREATNESS!

[INFO] This challenge will perform a bunch of checks.
[INFO] If you pass these checks, you will receive the /flag file.

[TEST] You should have redirected my stdout to a file called myflag. Checking...

[PASS] The file at the other end of my stdout looks okay!
[PASS] Success! You have satisfied all execution requirements.
hacker@piping~redirecting-more-output:~$ cat myflag

[FLAG] Here is your flag:
[FLAG] pwn.college{sjqVHrIcZ6G2p70AXK1PxsBAcqu.dVjN1QDL1IzN0czW}

```

### Challenge 3: Appending output
Here, we learn that the ` > ` character, when repeated for the same file, overwrites the previous data, hence losing the original data in the process.
The ` >> ` character is introduced which, instead, appends the previous file instead of overwriting it. Hence, resulting in no data loss.
This challenge, emphasises on the importance of this character by breaking the flag in two halves.

```
hacker@piping~appending-output:~$ /challenge/run >> ~/the-flag
[INFO] WELCOME! This challenge makes the following asks of you:
[INFO] - the challenge will check that output is redirected to a specific file path : /home/hacker/the-flag

[HYPE] ONWARDS TO GREATNESS!

[INFO] This challenge will perform a bunch of checks.
[INFO] Good luck!

[TEST] You should have redirected my stdout to a file called /home/hacker/the-flag. Checking...

[HINT] File descriptors are inherited from the parent, unless the FD_CLOEXEC is set by the parent on the file descriptor.
[HINT] For security reasons, some programs, such as python, do this by default in certain cases. Be careful if you are
[HINT] creating and trying to pass in FDs in python.

[PASS] The file at the other end of my stdout looks okay!
[PASS] Success! You have satisfied all execution requirements.
I will write the flag in two parts to the file /home/hacker/the-flag! I'll do
the first write directly to the file, and the second write, I'll do to stdout
(if it's pointing at the file). If you redirect the output in append mode, the
second write will append to (rather than overwrite) the first write, and you'll
get the whole flag!
hacker@piping~appending-output:~$ cat ~/the-flag
  |
 \|/ This is the first half:
  v
pwn.college{I45EZMkZzeZLm2RilZSLUwlLM2W.ddDM5QDL1IzN0czW}
                                                            ^
                  that is the second half /|\
                                                            |

If you only see the second half above, you redirected in *truncate* mode (>)

rather than *append* mode (>>), and so the write of the second half to stdout
overwrote the initial write of the first half directly to the file. Try append
mode!

```

### Challenge 4: Redirecting errors
Here, we are introduced to *__File Descriptor Numbers__*.
File Descriptor (FD) is a number the describes a communication channel in Linux.
The three types of FD are: 
+ FD 0: Standard Input 
+ FD 1: Standard Output 
+ FD 2: Standard Error
` > ` without a number basically means ` 1> `, which redirects FD 1.
Similarly we can replace the other 2 ***FDs***
In this challenge, we need to replace the output of `/challenge/run` to `myflag` and the errors to `instructions`.

```
hacker@piping~redirecting-errors:~$ /challenge/run > myflag 2> instructions
hacker@piping~redirecting-errors:~$ cat myflag
[FLAG] Here is your flag:
[FLAG] pwn.college{AC7_EIVnk3eL535tYj-TD7H7FPU.ddjN1QDL1IzN0czW}

```

### Challenge 5: Redirecting input
To redirect input  to programs we can use the `<` command.

```
hacker@piping~redirecting-input:~$ echo COLLEGE > PWN
hacker@piping~redirecting-input:~$ /challenge/run < PWN
Reading from standard input...
Correct! You have redirected the PWN file into my standard input, and I read
the value 'COLLEGE' out of it!
Here is your flag:
pwn.college{I1clmtrLm6yXZWTD6vdnsOmtOdt.dBzN1QDL1IzN0czW}

```

### Challenge 6: Grepping stored results
This challenge, combines the knowledge of the `grep` command and `>` command to get the flag.
Recalling, `grep` command is used to search for a specific string in a file that might contain loads of other data.

```
hacker@piping~grepping-stored-results:~$ /challenge/run > /tmp/data.txt
[INFO] WELCOME! This challenge makes the following asks of you:
[INFO] - the challenge will check that output is redirected to a specific file path : /tmp/data.txt
[INFO] - the challenge will output a reward file if all the tests pass : /challenge/.data.txt
[HYPE] ONWARDS TO GREATNESS!

[INFO] This challenge will perform a bunch of checks.
[INFO] If you pass these checks, you will receive the /challenge/.data.txt file.

[TEST] You should have redirected my stdout to a file called /tmp/data.txt. Checking...

[HINT] File descriptors are inherited from the parent, unless the FD_CLOEXEC is set by the parent on the file descriptor.
[HINT] For security reasons, some programs, such as python, do this by default in certain cases. Be careful if you are
[HINT] creating and trying to pass in FDs in python.

[PASS] The file at the other end of my stdout looks okay!
[PASS] Success! You have satisfied all execution requirements.
hacker@piping~grepping-stored-results:~$ grep pwn.college /tmp/data.txt
pwn.college{s1Dm8EeYtECNKuyV6jrkviLFqal.dhTM4QDL1IzN0czW}

```

### Challenge 7: Grepping live output
To reduce the work of storing the results in a file and then executing it, we can use the ` | `(pipe) operator.
Stdout from the command to the left of the pipe will be connected to (piped into) the stdin of the command to the right of the pipe.

```
hacker@piping~grepping-live-output:~$ /challenge/run | grep pwn.college
[INFO] WELCOME! This challenge makes the following asks of you:
[INFO] - the challenge checks for a specific process at the other end of stdout : grep
[INFO] - the challenge will output a reward file if all the tests pass : /challenge/.data.txt

[HYPE] ONWARDS TO GREATNESS!

[INFO] This challenge will perform a bunch of checks.
[INFO] If you pass these checks, you will receive the /challenge/.data.txt file.

[TEST] You should have redirected my stdout to another process. Checking...
[TEST] Performing checks on that process!

[INFO] The process' executable is /nix/store/xpq4yhadyhazkcsggmqd7rsgvxb3kjy4-gnugrep-3.11/bin/grep.
[INFO] This might be different than expected because of symbolic links (for example, from /usr/bin/python to /usr/bin/python3 to /usr/bin/python3.8).
[INFO] To pass the checks, the executable must be grep.

[PASS] You have passed the checks on the process on the other end of my stdout!
[PASS] Success! You have satisfied all execution requirements.
pwn.college{UIcJVGGLvixgqgSeWnUvbhIaCjw.dlTM4QDL1IzN0czW}

```

### Challenge 8: Grepping errors
The `|` operator redirects only ***standard output*** to another program. 
There is no ` 2| ` form of the operator.
In order to redirect a ***file descriptor to another file descriptor*** we use the `>&` operator.
Thus, we redirect stderr to stdout (2>& 1) and then pipe the now-combined stderr and stdout as normal (|)

```
hacker@piping~grepping-errors:~$ /challenge/run 2>& 1 | grep pwn.college
[INFO] WELCOME! This challenge makes the following asks of you:
[INFO] - the challenge checks for a specific process at the other end of stderr : grep
[INFO] - the challenge will output a reward file if all the tests pass : /challenge/.data.txt

[HYPE] ONWARDS TO GREATNESS!

[INFO] This challenge will perform a bunch of checks.
[INFO] If you pass these checks, you will receive the /challenge/.data.txt file.

[TEST] You should have redirected my stderr to another process. Checking...
[TEST] Performing checks on that process!

[INFO] The process' executable is /nix/store/xpq4yhadyhazkcsggmqd7rsgvxb3kjy4-gnugrep-3.11/bin/grep.
[INFO] This might be different than expected because of symbolic links (for example, from /usr/bin/python to /usr/bin/python3 to /usr/bin/python3.8).
[INFO] To pass the checks, the executable must be grep.

[PASS] You have passed the checks on the process on the other end of my stderr!
[PASS] Success! You have satisfied all execution requirements.
pwn.college{cEx5BpTVRhwe4z_qjbZ6oK10N5P.dVDM5QDL1IzN0czW}

```

### Challenge 9: Duplicating piped data with tee
Intercept the commands `/challenge/pwn` and `/challenge/college` by using `tee`

```
hacker@piping~duplicating-piped-data-with-tee:~$ /challenge/pwn | tee flag | /challenge/college
The input to 'college' does not contain the correct secret code! This code
should be provided by the 'pwn' command. HINT: use 'tee' to intercept the
output of 'pwn' and figure out what the code needs to be.
```

Now `cat` the flag:

```
hacker@piping~duplicating-piped-data-with-tee:~$ cat flag
Usage: /challenge/pwn --secret [SECRET_ARG]

SECRET_ARG should be "85q8euF1"
```

Now, using the secret argument provided:

```
hacker@piping~duplicating-piped-data-with-tee:~$ /challenge/pwn --secret 85q8euF1 | /challenge/college
Processing...
Correct! Passing secret value to /challenge/college...
Great job! Here is your flag:
pwn.college{85q8euF1ozhLqxWd3NH6W0aflDs.dFjM5QDL1IzN0czW}

```

### Challenge 10: Writing to multiple programs


```

```

### Challenge 11: Split-piping stdder and stdout


```

```
