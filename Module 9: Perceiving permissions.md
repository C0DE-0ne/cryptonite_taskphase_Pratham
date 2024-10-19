# Changing file ownership
We cannot access files and programs if it's under our user account(even if it's the same system)
Here the challenge requires us to change the ower of a file using `chown` command.

Command line:

```
hacker@permissions~changing-file-ownership:~$ cat /flag
cat: /flag: Permission denied
hacker@permissions~changing-file-ownership:~$ chown hacker /flag
hacker@permissions~changing-file-ownership:~$ cat /flag
pwn.college{A-w0Cnzx3w9AN-d_OPwLRLC2lrs.dFTM2QDL4ADO0czW}
```

# Group and files
Same as before but instead of a single user the file is owned by a group of users.
For the flag we first use the command `ls -1` to find the file with the flag and then change the owner of the group using command `chgrp`.

Command line:

```
hacker@permissions~groups-and-files:~$ ls -1
COLLEGE
PWN
a
asdf
cat
dog
doracake
instructions
key
myflag
not-the-flag
pwn
the-flag
hacker@permissions~groups-and-files:~$ cat not-the-flag
cat: not-the-flag: Permission denied
hacker@permissions~groups-and-files:~$ chgrp hacker not-the-flag
hacker@permissions~groups-and-files:~$ cat not-the-flag
pwn.college{06KrW_4hS9-No2EJIcbckSR4rAQ.dFzNyUDL4ADO0czW}
```

# Fun with groups names
The file containing the flag is in a group unknown to us, so we have to find the group using command `id`.
Then change group owener for access.

Command line:

```
hacker@permissions~fun-with-groups-names:~$ id
uid=1000(hacker) gid=1000(grp24055) groups=1000(grp24055)
hacker@permissions~fun-with-groups-names:~$ ls -1

COLLEGE
PWN
a
asdf
cat
dog
doracake
instructions
key
myflag
not-the-flag
pwn
the-flag
hacker@permissions~fun-with-groups-names:~$ chgrp grp24055 not-the-flag
hacker@permissions~fun-with-groups-names:~$ cat not-the-flag
pwn.college{A7vLUsQwNVnt8Hb5oRYsJomHLOJ.dJzNyUDL4ADO0czW}
```

# Changing permissions
We can change permissions uisng `chmod` command, for the flag we must change permission for /flag file. 
Command line:

```
hacker@permissions~changing-permissions:~$ cat /flag
cat: /flag: Permission denied
hacker@permissions~changing-permissions:~$ chmod o+r /flag
hacker@permissions~changing-permissions:~$ cat /flag
pwn.college{YTkPH5BbO1aqW7zr5oo56oVIGDV.dNzNyUDL4ADO0czW}
```

# Executable files


Command line:

```
hacker@permissions~executable-files:~$ chmod o+x /challenge/run
hacker@permissions~executable-files:~$ /challenge/run
ssh-entrypoint: /challenge/run: Permission denied
hacker@permissions~executable-files:~$ chmod a+x /challenge/run
hacker@permissions~executable-files:~$ /challenge/run
Successful execution! Here is your flag:
pwn.college{MPIBFscUZpk8rkvRzehNdJyZsFw.dJTM2QDL4ADO0czW}
```

# Permission tweaking practice 
We have to use the `chmod` command and solve 8 challenge that requires to challenge permissions.
(The 8 challenges have too much lines so I thought it wouldn't look good)

Command line:
```
You set the correct permissions!
You've solved all 8 rounds! I have changed the ownership
of the /flag file so that you can 'chmod' it. You won't be able to read
it until you make it readable with chmod!

Current permissions of "/flag": ---------
-  the user doesn't have read permissions
- the user doesn't have write permissions
- the user doesn't have execute permissions
- the group doesn't have read permissions
- the group doesn't have write permissions
- the group doesn't have execute permissions
- the world doesn't have read permissions
- the world doesn't have write permissions
- the world doesn't have execute permissions
hacker@permissions~permission-tweaking-practice:~$ chmod u+r /flag
hacker@permissions~permission-tweaking-practice:~$ cat /flag
pwn.college{gNgqkkFOrqB4_imU32bMJbS2kvh.dBTM2QDL4ADO0czW}
```

# Permissions setting practice
Same as above but we make use of = (which sets the given persmissions and wipes out the rest) and , (we chain multiple mods to chmod).

Command line:
```
You set the correct permissions!

You've solved all 8 rounds! I have changed the ownership
of the /flag file so that you can 'chmod' it. You won't be able to read
it until you make it readable with chmod!
Current permissions of "/flag": ---------
- the user doesn't have read permissions
- the user doesn't have write permissions
- the user doesn't have execute permissions
- the group doesn't have read permissions
- the group doesn't have write permissions
- the group doesn't have execute permissions
- the world doesn't have read permissions
- the world doesn't have write permissions
- the world doesn't have execute permissions
hacker@permissions~permissions-setting-practice:~$ chmod u=r /flag
hacker@permissions~permissions-setting-practice:~$ cat /flag
pwn.college{8Pm1l0EXCWbck9OoECRCJ2CXkck.dNTM5QDL4ADO0czW}
```

# The SUID bit 
In this challenge we set a SUID(set user id), to get the flag we set the SUID and then run the program which inturn bring a shell to cat the flag in. 

Command line:

```
hacker@permissions~the-suid-bit:~$ chmod u+s /challenge/getroot
hacker@permissions~the-suid-bit:~$ /challenge/getroot
SUCCESS! You have set the suid bit on this program, and it is running as root!
Here is your shell...
root@permissions~the-suid-bit:~# cat /flag
pwn.college{AWtnRc2hpbGDdMQb4mh0AKoDZS-.dNTM2QDL4ADO0czW}
```
