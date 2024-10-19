# Chaining with semicolons
Here we make use of  `;` (which is used to chain together commands). For the flag we chain together `/challenge/pwn` and `/challenge/run`.

Command line:

```
hacker@chaining~chaining-with-semicolons:~$ /challenge/pwn;/challenge/college
Yes! You chained /challenge/pwn and /challenge/college! Here is your flag:
pwn.college{8UF93-Ob5IOSWFEn4PdIogH_0L-.dVTN4QDL4ADO0czW}
```

# Your first shell script
If we have execute multiple commands chaining using `;` length of the chsin becomes too big and annoying to deal with. 
So we creat a shell script using the command `nano` . For the flag we create a script `x.sh` which runs `/challenge/pwn` and then `/challenge/college` and run the bash.

Command line:
```
hacker@chaining~your-first-shell-script:~$ nano x.sh
hacker@chaining~your-first-shell-script:~$ bash x.sh
Great job, you've written your first shell script! Here is the flag:
pwn.college{sQuAWGl6Ue352BqugUgV5wOIZq5.dFzN4QDL4ADO0czW}
```

# Redirecting script output
We make a script same as the challenge before, but this time we pipe the output to `/challenge/solve`.

Command line:
```
hacker@chaining~redirecting-script-output:~$ nano x.sh
hacker@chaining~redirecting-script-output:~$ bash x.sh | /challenge/solve
Correct! Here is your flag:
pwn.college{shUxUhXfW5jneFflXAPRDGA80V2.dhTM5QDL4ADO0czW}
```

# Executabe shell scripts
The challenge requires us to invoke `/challenge/solve` in a script without using bash to execute it and giving it permission using `chmod` to execute it.
Command line:

```
hacker@chaining~executable-shell-scripts:~$ nano s.sh
hacker@chaining~executable-shell-scripts:~$ chmod u+x s.sh
hacker@chaining~executable-shell-scripts:~$ ./s.sh
Congratulations on your shell script execution! Your flag:
pwn.college{8onN2-vVrMoXjoXFEboOQO0FQGg.dRzNyUDL4ADO0czW}
```
