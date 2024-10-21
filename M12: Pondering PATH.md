# Module 12: Pondering Path

### Challenge 1: The path Variable

```
hacker@path~the-path-variable:~$ PATH=""
hacker@path~the-path-variable:~$ rm /challenge/run
ssh-entrypoint: rm: No such file or directory
hacker@path~the-path-variable:~$ /challenge/run
Trying to remove /flag...
/challenge/run: line 4: rm: No such file or directory
The flag is still there! I might as well give it to you!
pwn.college{U2SGvsEpTRSIPB1sgsrC_tfJHzv.dZzNwUDL1IzN0czW}

```

### Challenge 2: Setting PATH

```
hacker@path~setting-path:~$ PATH=/challenge/more_commands
hacker@path~setting-path:~$ /challenge/run
Invoking 'win'....
Congratulations! You properly set the flag and 'win' has launched!
pwn.college{kNUq0olm_iIiwWkFpb6-OMrCyfP.dVzNyUDL1IzN0czW}

```

### Challenge 3: Adding Commands
```hacker@path~adding-commands:~$ touch win
hacker@path~adding-commands:~$ echo $PATH
/run/challenge/bin:/run/workspace/bin:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin
hacker@path~adding-commands:~$ PATH=/run/challenge/bin:/run/workspace/bin:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin:/home/hacker
hacker@path~adding-commands:~$ chmod u+x win
hacker@path~adding-commands:~$ echo "cat /flag" > win
hacker@path~adding-commands:~$ /challenge/run
Invoking 'win'....
pwn.college{Io29MGf3TuPxfMraNE13dqSCTQW.dZzNyUDL1IzN0czW}

```

### Challenge 4: Hijacking Commands

```
hacker@path~hijacking-commands:~$ touch rm
hacker@path~hijacking-commands:~$ find / -name cat
find: ‘/tmp/tmp.MiOQGWw5Zc’: Permission denied
find: ‘/etc/ssl/private’: Permission denied
/usr/bin/cat
/usr/share/doc/zsh-common/examples/Functions/cat
find: ‘/var/cache/apt/archives/partial’: Permission denied
find: ‘/var/cache/ldconfig’: Permission denied
find: ‘/var/cache/private’: Permission denied
find: ‘/var/lib/apt/lists/partial’: Permission denied
find: ‘/var/lib/mysql-files’: Permission denied
find: ‘/var/lib/private’: Permission denied
find: ‘/var/lib/mysql’: Permission denied
find: ‘/var/lib/mysql-keyring’: Permission denied
find: ‘/var/lib/php/sessions’: Permission denied
find: ‘/var/log/private’: Permission denied
find: ‘/var/log/apache2’: Permission denied
find: ‘/var/log/mysql’: Permission denied
/run/workspace/bin/cat
find: ‘/run/mysqld’: Permission denied
find: ‘/run/sudo’: Permission denied
find: ‘/root’: Permission denied
/opt/busybox/busybox-1.33.2/_install/bin/cat
/opt/busybox/busybox-1.33.2/testsuite/cat
/opt/aflplusplus/nyx_mode/packer/linux_initramfs/rootTemplate/bin/cat
find: ‘/proc/tty/driver’: Permission denied
find: ‘/proc/1/task/1/fd’: Permission denied
find: ‘/proc/1/task/1/fdinfo’: Permission denied
find: ‘/proc/1/task/1/ns’: Permission denied
find: ‘/proc/1/fd’: Permission denied
find: ‘/proc/1/map_files’: Permission denied
find: ‘/proc/1/fdinfo’: Permission denied
find: ‘/proc/1/ns’: Permission denied
find: ‘/proc/7/task/7/fd’: Permission denied
find: ‘/proc/7/task/7/fdinfo’: Permission denied
find: ‘/proc/7/task/7/ns’: Permission denied
find: ‘/proc/7/fd’: Permission denied
find: ‘/proc/7/map_files’: Permission denied
find: ‘/proc/7/fdinfo’: Permission denied
find: ‘/proc/7/ns’: Permission denied
/nix/store/mjnsl8dps0vn3aaf9wpgk4n830x320a7-dojo-workspace-full/bin/cat
/nix/store/cakzg9vppcbxwq046nlbi6xmib3xx4ka-dojo-workspace-full/bin/cat
/nix/store/kgvkx02gx2gx1zk6q0cvbif69pwpnfl9-dojo-workspace-full/bin/cat
/nix/store/6sin45s97yp4cfdn3q74drsjd7f4cq1f-dojo-workspace-full/bin/cat
/nix/store/nlxcqrgiszbjqkq86qhnflrbrs4adaac-dojo-workspace-full/bin/cat
/nix/store/qi268adp91zwql0rc6lkjk35mz6c6r1x-dojo-workspace-full/bin/cat
/nix/store/k71apxkm38m3g34k01sb6zhysi0y7gph-coreutils-9.5/bin/cat
/nix/store/36wi32s36mg3wxqhm067gvcc2f6p38pw-dojo-workspace-full/bin/cat
/nix/store/a18ji16bi5ws1zksk1jwrx8dir6rdbhi-dojo-workspace-full/bin/cat
/nix/store/nsh8bjqlami5grymm2mv63plmncga7wk-dojo-workspace-full/bin/cat
/nix/store/gjm9q2lqa3j406za97nchbb670vlfklj-dojo-workspace-full/bin/cat
/nix/store/vapa6rnwfvbm3srldx33nyy2ybz9iqpy-dojo-workspace-full/bin/cat
/nix/store/hgcmc7ps7wr0sxnbc87g4ba970km2vy4-dojo-workspace-full/bin/cat
/nix/store/cq9lnzgc12bx6i443vgnji7ccfb2j2wl-dojo-workspace-full/bin/cat
/nix/store/h8k7v1w69b9fs60jkx59vkhpy6scwgap-dojo-workspace-full/bin/cat
/nix/store/r0ln7hlmzk9z34kbqwlb12zgf4c34x9c-dojo-workspace-full/bin/cat
hacker@path~hijacking-commands:~$ echo "/usr/bin/cat /flag" > rm
hacker@path~hijacking-commands:~$ chmod u+x rm
hacker@path~hijacking-commands:~$ PATH=/home/hacker
hacker@path~hijacking-commands:~$ /challenge/run
Trying to remove /flag...
pwn.college{YiCJYi9QqwgUhzORqq71stzA_tr.ddzNyUDL1IzN0czW}

```
