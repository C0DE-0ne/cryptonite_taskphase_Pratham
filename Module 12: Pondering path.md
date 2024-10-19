# The path variable

Command line:

```
hacker@path~the-path-variable:~$ PATH=""
hacker@path~the-path-variable:~$ /challenge/run
Trying to remove /flag...
/challenge/run: line 4: rm: No such file or directory
The flag is still there! I might as well give it to you!
pwn.college{skRDGcyF2P0n4na1Jpql0TtW5Ds.dZzNwUDL4ADO0czW}
```

# Setting path

Command line:

```
hacker@path~setting-path:~$ PATH=/challenge/more_commands
hacker@path~setting-path:~$ /challenge/run
Invoking 'win'....
Congratulations! You properly set the flag and 'win' has launched!
pwn.college{YdOQY7_46MkzXp-S49TO3PTUEue.dVzNyUDL4ADO0czW}
```

# Adding commands

Command line:

```
hacker@path~adding-commands:~$ touch win
hacker@path~adding-commands:~$ nano win
hacker@path~adding-commands:~$ echo $PATH
/run/challenge/bin:/run/workspace/bin:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin
hacker@path~adding-commands:~$ export PATH=/home/hacker:$PATH
hacker@path~adding-commands:~$ echo $PATH
/home/hacker:/run/challenge/bin:/run/workspace/bin:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin
hacker@path~adding-commands:~$ chmod a+x /home/hacker/win
hacker@path~adding-commands:~$ /challenge/run
Invoking 'win'....
pwn.college{0MV3bv5dfzFxROAyFETd-pCqhPY.dZzNyUDL4ADO0czW}
```

# Hijacking commands

Command line:

```
hacker@path~hijacking-commands:~$ nano rm
hacker@path~hijacking-commands:~$ chmod a+x rm
hacker@path~hijacking-commands:~$ PATH=/home/hacker
hacker@path~hijacking-commands:~$ /challenge/run
Trying to remove /flag...
pwn.college{wLxVBSWe7xlr4wbk7SlQ-j0gx_f.ddzNyUDL4ADO0czW}
```
