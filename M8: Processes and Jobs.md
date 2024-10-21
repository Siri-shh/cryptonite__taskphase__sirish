# Module 8: Processes and Jobs

### Challenge 1: Listing Processes

```
hacker@processes~listing-processes:~$ ps -aux
USER         PID %CPU %MEM    VSZ   RSS TTY      STAT START   TIME COMMAND
root           1  0.1  0.0   1056   640 ?        Ss   10:36   0:00 /sbin/docker-init -- /nix/var/nix/profiles/default/bin/dojo-init /run/dojo/bi
root           7  0.0  0.0   5052  2240 ?        S    10:36   0:00 /run/dojo/bin/sleep 6h
root          68  0.0  0.0   4132  2560 ?        S    10:36   0:00 /challenge/27527-run-4794
root          72  0.0  0.0   2744  1600 ?        S    10:36   0:00 sleep 6h
hacker        73  0.1  0.0   5240  3840 pts/0    Ss   10:36   0:00 /run/dojo/bin/ssh-entrypoint
hacker        91  0.0  0.0   7868  3520 pts/0    R+   10:36   0:00 ps -aux
hacker@processes~listing-processes:~$ /challenge/27527-run-4794
Yahaha, you found me! Here is your flag:
pwn.college{wBsSObFvV_mFlhfnMFUUckVB5jI.dhzM4QDL1IzN0czW}

```

### Challenge 2: Killing Processes

```
hacker@processes~killing-processes:~$ ps -ef
UID          PID    PPID  C STIME TTY          TIME CMD
root           1       0  0 10:45 ?        00:00:00 /sbin/docker-init -- /ni
root           7       1  0 10:45 ?        00:00:00 /run/dojo/bin/sleep 6h
root          71       1  0 10:45 ?        00:00:00 su -c /challenge/.launch
hacker        73      71  0 10:45 ?        00:00:00 /challenge/dont_run
hacker        74      73  0 10:45 ?        00:00:00 sleep 6h
hacker        75       0  0 10:45 pts/0    00:00:00 /run/dojo/bin/ssh-entryp
hacker        98      75  0 10:48 pts/0    00:00:00 ps -ef
hacker@processes~killing-processes:~$ kill 73
hacker@processes~killing-processes:~$ /challenge/run
Great job! Here is your payment:
pwn.college{sh8WuIqMi6ZTuW9tEOUNKibRkm6.dJDN4QDL1IzN0czW}

```

### Challenge 3: Interrupting Processes

```
hacker@processes~interrupting-processes:~$ /challenge/run
I could give you the flag... but I won't, until this process exits. Remember,
you can force me to exit with Ctrl-C. Try it now!
^C
Good job! You have used Ctrl-C to interrupt this process! Here is your flag:
pwn.college{sTuC5BiReAx5ueX8ef84YEkrqE8.dNDN4QDL1IzN0czW}

```

### Challenge 4: Suspending Processes

```
hacker@processes~suspending-processes:~$ /challenge/run
I'll only give you the flag if there's already another copy of me running in
this terminal... Let's check!

UID          PID    PPID  C STIME TTY          TIME CMD
root          83      65  0 16:33 pts/0    00:00:00 bash /challenge/run
root          85      83  0 16:33 pts/0    00:00:00 ps -f

I don't see a second me!

To pass this level, you need to suspend me and launch me again! You can
background me with Ctrl-Z or, if you're not ready to do that for whatever
reason, just hit Enter and I'll exit!
^Z
[1]+  Stopped                 /challenge/run
hacker@processes~suspending-processes:~$ /challenge/run
I'll only give you the flag if there's already another copy of me running in

this terminal... Let's check!

UID          PID    PPID  C STIME TTY          TIME CMD
root          83      65  0 16:33 pts/0    00:00:00 bash /challenge/run
root          90      65  0 16:38 pts/0    00:00:00 bash /challenge/run
root          92      90  0 16:38 pts/0    00:00:00 ps -f

Yay, I found another version of me! Here is the flag:
pwn.college{QBbFQP2KtB-GpwdetQcM2LdFrTD.dVDN4QDL1IzN0czW}

```

### Challenge 5: Resuming Processes

```
hacker@processes~resuming-processes:~$ /challenge/run
Let's practice resuming processes! Suspend me with Ctrl-Z, then resume me with
the 'fg' command! Or just press Enter to quit me!
^Z
[1]+  Stopped                 /challenge/run
hacker@processes~resuming-processes:~$ fg
/challenge/run
I'm back! Here's your flag:
pwn.college{M7czWuULm080JbBVL7JH5cnJ5Mw.dZDN4QDL1IzN0czW}
Don't forget to press Enter to quit me!

Goodbye!

```

### Challenge 6: Backgrounding Processes

```
hacker@processes~backgrounding-processes:~$ /challenge/run
I'll only give you the flag if there's already another copy of me running *and
not suspended* in this terminal... Let's check!

UID          PID STAT CMD
root          82 S+   bash /challenge/run
root          84 R+   ps -o user=UID,pid,stat,cmd

I don't see a second me!

To pass this level, you need to suspend me, resume the suspended process in the
background, and then launch a new version of me! You can background me with
Ctrl-Z (and resume me in the background with 'bg') or, if you're not ready to
do that for whatever reason, just hit Enter and I'll exit!
^Z
[1]+  Stopped                 /challenge/run
hacker@processes~backgrounding-processes:~$ bg
[1]+ /challenge/run &



Yay, I'm now running the background! Because of that, this text will probably
overlap weirdly with the shell prompt. Don't panic; just hit Enter a few times
to scroll this text out.
hacker@processes~backgrounding-processes:~$ /challenge/run
I'll only give you the flag if there's already another copy of me running *and
not suspended* in this terminal... Let's check!

UID          PID STAT CMD
root          82 S    bash /challenge/run
root          92 S    sleep 6h
root          93 S+   bash /challenge/run
root          95 R+   ps -o user=UID,pid,stat,cmd

Yay, I found another version of me running in the background! Here is the flag:
pwn.college{YZzr6wUbvUGr9pi7zimjMM85sGT.ddDN4QDL1IzN0czW}

```

### Challenge 7: Foregrounding Processes 

```hacker@processes~foregrounding-processes:~$ /challenge/run
To pass this level, you need to suspend me, resume the suspended process in the
background, and *then* foreground it without re-suspending it! You can
background me with Ctrl-Z (and resume me in the background with 'bg') or, if
you're not ready to do that for whatever reason, just hit Enter and I'll exit!
^Z
[1]+  Stopped                 /challenge/run
hacker@processes~foregrounding-processes:~$ bg
[1]+ /challenge/run &

Yay, I'm now running the background! Because of that, this text will probably
overlap weirdly with the shell prompt. Don't panic; just hit Enter a few times
to scroll this text out. After that, resume me into the foreground with 'fg';
I'll wait.
hacker@processes~foregrounding-processes:~$ fg
/challenge/run
YES! Great job! I'm now running in the foreground. Hit Enter for your flag!

pwn.college{k6NvAk7xNFtkg3GCspa-4a-6q4d.dhDN4QDL1IzN0czW}

```

### Challenge 8: Starting Backgrounded Processes

```
hacker@processes~starting-backgrounded-processes:~$ /challenge/run &
[1] 82

Yay, you started me in the background! Because of that, this text will probably
overlap weirdly with the shell prompt, but you're used to that by now...

Anyways! Here is your flag!
pwn.college{E5J3f9RioIh4v-i9TL9vP5JFSLV.dlDN4QDL1IzN0czW}
[1]+  Done                    /challenge/run

```


### Challenge 9: Proccess Exit Codes

```
hacker@processes~process-exit-codes:~$ /challenge/get-code
Exiting with an error code!
hacker@processes~process-exit-codes:~$ echo $?
97
hacker@processes~process-exit-codes:~$ /challenge/submit-code 97
CORRECT! Here is your flag:
pwn.college{MlEbInGWRa8pT9emKvMM35xJ5T0.dljN4UDL1IzN0czW}

```
