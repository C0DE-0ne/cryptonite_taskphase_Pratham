# Listing processes

Command line:

`hacker@processes~listing-processes:~$ ps aux`

USER         PID %CPU %MEM    VSZ   RSS TTY      STAT START   TIME COMMAND

root           1  0.0  0.0   1056   640 ?        Ss   17:41   0:00 /sbin/docker-init -- /nix/var/nix/profiles/default/bin/dojo-i

root           7  0.0  0.0   5052  2240 ?        S    17:41   0:00 /run/dojo/bin/sleep 6h

root          68  0.0  0.0   4132  2560 ?        S    17:41   0:00 /challenge/9868-run-17456

root          72  0.0  0.0   2744  1600 ?        S    17:41   0:00 sleep 6h

hacker        73  0.0  0.0   5372  3840 pts/1    Ss   17:41   0:00 /run/dojo/bin/ssh-entrypoint

hacker        79  0.0  0.0   5240  3840 pts/0    Ss+  17:41   0:00 /run/dojo/bin/ssh-entrypoint

hacker       109  0.0  0.0   7868  3200 pts/1    R+   17:43   0:00 ps aux

`hacker@processes~listing-processes:~$ /challenge/9868-run-17456`

Yahaha, you found me! Here is your flag:

pwn.college{seG3r60aO8BTS6cZ_flNhzbWM7f.dhzM4QDL4ADO0czW}

# Killing Processes
To complete the challenge we use the kill command.So using ps to get the PID(I used -ef at first and didn't get it then i used aux as the agruement).
After killing the process we run given program.

Command line:

`hacker@processes~killing-processes:~$ ps aux | grep /challenge/dont_run`

hacker        73  0.0  0.0   4976  3200 ?        Ss   17:58   0:00 /challenge/dont_run

hacker        98  0.0  0.0   4140  2240 pts/0    S+   17:59   0:00 grep --color=auto /challenge/dont_run

`hacker@processes~killing-processes:~$ kill 73`

`hacker@processes~killing-processes:~$ /challenge/run`

Great job! Here is your payment:

pwn.college{09SzZ305m9eLUZ5pda5u0TWpNJf.dJDN4QDL4ADO0czW}

# Interrupting processes
If we want get rid of a process waiting in the termial we can we use the hotket ctrl c.
To get the flag we must interrupt /challenge/run

Command line:

`hacker@processes~interrupting-processes:~$ /challenge/run`

I could give you the flag... but I won't, until this process exits. Remember,
you can force me to exit with Ctrl-C. Try it now!

`^C`
Good job! You have used Ctrl-C to interrupt this process! Here is your flag:

pwn.college{wUE09nl0cuWgr_w7pcUAnOeGWGk.dNDN4QDL4ADO0czW}

# Suspending processes
Here we use ctrl-z which only suspends the process in the background.
The is given when we supsend /challenge/run once run it again in the same termial

Command line:

`hacker@processes~suspending-processes:~$ /challenge/run`

I'll only give you the flag if there's already another copy of me running in
this terminal... Let's check!

UID          PID    PPID  C STIME TTY          TIME CMD

root          99      71  0 18:16 pts/1    00:00:00 bash /challe

root         101      99  0 18:16 pts/1    00:00:00 ps -f

I don't see a second me!

To pass this level, you need to suspend me and launch me again! You can
background me with Ctrl-Z or, if you're not ready to do that for whatever
reason, just hit Enter and I'll exit!

`^Z`

[1]+  Stopped                 /challenge/run

`hacker@processes~suspending-processes:~$ /challenge/run`

I'll only give you the flag if there's already another copy of me running in
this terminal... Let's check!


UID          PID    PPID  C STIME TTY          TIME CMD

root          99      71  0 18:16 pts/1    00:00:00 bash /challe

root         106      71  0 18:16 pts/1    00:00:00 bash /challe

root         108     106  0 18:16 pts/1    00:00:00 ps -f

Yay, I found another version of me! Here is the flag:

pwn.college{QgLtUeJRC7JZ7ImOAAoDfufLyhe.dVDN4QDL4ADO0czW}

# Resuming processes
In the previous challenge we learn't to suspend here we will resume it using `fg`.
For the flag we'll suspend the program and resume it.

Command line;

`hacker@processes~resuming-processes:~$ /challenge/run`

Let's practice resuming processes! Suspend me with Ctrl-Z, then resume me with
the 'fg' command! Or just press Enter to quit me!

`^Z`

[1]+  Stopped                 /challenge/run

`hacker@processes~resuming-processes:~$ fg /challenge/run`

I'm back! Here's your flag:

pwn.college{EAn0FVOmu6w5zd_-M8F-HgfxTrY.dZDN4QDL4ADO0czW}

# Backgrounding Processes
After suspending the program we can run it in the background of the terminal.
To get the flag we suspend the program and the run it in the background and run it again in the terminal.

Command line:

`hacker@processes~backgrounding-processes:~$ /challenge/run`

I'll only give you the flag if there's already another copy of me running *and
not suspended* in this terminal... Let's check!


UID          PID STAT CMD

root          99 S+   bash /challenge/run

root         101 R+   ps -o user=UID,pid,stat,cmd


I don't see a second me!

To pass this level, you need to suspend me, resume the suspended process in the
background, and then launch a new version of me! You can background me with
Ctrl-Z (and resume me in the background with 'bg') or, if you're not ready to
do that for whatever reason, just hit Enter and I'll exit!

`^Z`

[1]+  Stopped                 /challenge/run

`hacker@processes~backgrounding-processes:~$ bg /challenge/run`

[1]+ /challenge/run &

hacker@processes~backgrounding-processes:~$


Yay, I'm now running the background! Because of that, this text will probably
overlap weirdly with the shell prompt. Don't panic; just hit Enter a few times
to scroll this text out.

`hacker@processes~backgrounding-processes:~$ /challenge/run`

I'll only give you the flag if there's already another copy of me running *and
not suspended* in this terminal... Let's check!


UID          PID STAT CMD

root          99 S    bash /challenge/run

root         109 S    sleep 6h

root         110 S+   bash /challenge/run

root         112 R+   ps -o user=UID,pid,stat,cmd

Yay, I found another version of me running in the background! Here is the flag:

pwn.college{8SWvMwbU7iRnhSEK8wLN8Y64wCN.ddDN4QDL4ADO0czW}

# Foregrounding processes
Here to get the flag we suspend the program, resume it in the background using `bg` and then foregrounding it using `fg`.
Command line:

`hacker@processes~foregrounding-processes:~$ /challenge/run`
To pass this level, you need to suspend me, resume the suspended process in the
background, and *then* foreground it without re-suspending it! You can
background me with Ctrl-Z (and resume me in the background with 'bg') or, if
you're not ready to do that for whatever reason, just hit Enter and I'll exit!

`^Z`

[1]+  Stopped                 /challenge/run

`hacker@processes~foregrounding-processes:~$ bg /challenge/run`

[1]+ /challenge/run &


Yay, I'm now running the background! Because of that, this text will probably
overlap weirdly with the shell prompt. Don't panic; just hit Enter a few times
to scroll this text out. After that, resume me into the foreground with 'fg';
I'll wait.

`hacker@processes~foregrounding-processes:~$ fg /challenge/run`

/challenge/run

YES! Great job! I'm now running in the foreground. Hit Enter for your flag!

pwn.college{4lh11iF6GNwAxLSjlvbyppyKaf0.dhDN4QDL4ADO0czW}

# Starting Backgrounded processes
We can start a process right in the background without using bg, by using `&`.
To get the flag we run `/challenge/run` in the background from the start.

Command line:

`hacker@processes~starting-backgrounded-processes:~$ /challenge/run &`

[1] 99

Yay, you started me in the background! Because of that, this text will probably
overlap weirdly with the shell prompt, but you're used to that by now...
Anyways! Here is your flag!

pwn.college{oTOIWDtQIE9vVGAXBBwsVBRLKDG.dlDN4QDL4ADO0czW}

[1]+  Done                    /challenge/run

# Process Exit codes
Every shell command, including every program and every builtin, exits with an exit code when it finishes running and terminates.
So 0 means no errors and commands that fails gives a non-zero number.
To get the flag we must retrieve the exit code returned by /challenge/get-code and then run /challenge/submit-code with that error code as an argument

Command line:

`hacker@processes~process-exit-codes:~$ /challenge/get-code`

Exiting with an error code!

`hacker@processes~process-exit-codes:~$ echo $?`

194

`hacker@processes~process-exit-codes:~$ /challenge/submit-code 194`

CORRECT! Here is your flag:

pwn.college{cXfc6UDqKVgXjMa4pSSrWxoEeLo.dljN4UDL4ADO0czW}
