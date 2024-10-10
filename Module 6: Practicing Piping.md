# Redirecting output
Here we use > to redirect the output. For the flag we have to redirct output of echo PWN into a file called COLLEGE.

Command line:

`
hacker@piping~redirecting-output:~$ echo PWN > COLLEGE
Correct! You successfully redirected 'PWN' to the file 'COLLEGE'! Here is your
flag:
pwn.college{ApX6I1rcy4o7BblvLnra7-Sb7ub.dRjN1QDL4ADO0czW}
`

# Redirecting more output
Here we have to do same as before for /challenge/run. by redirecting /challenge/run > myflag it says we have passed all tests and /flag file avavialbe, so we read the file using cat myflag.

Command line:

`
hacker@piping~redirecting-more-output:~$ /challenge/run > myflag
`

[INFO] WELCOME! This challenge makes the following asks of you:

[INFO] - the challenge will check that output is redirected to a specific file path : myflag

[INFO] - the challenge will output a reward file if all the tests pass : /flag

[HYPE] ONWARDS TO GREATNESS!

[INFO] This challenge will perform a bunch of checks.

[INFO] If you pass these checks, you will receive the /flag file.

[TEST] You should have redirected my stdout to a file called myflag. Checking...

[PASS] The file at the other end of my stdout looks okay!

[PASS] Success! You have satisfied all execution requirements.

`
hacker@piping~redirecting-more-output:~$ cat myflag
`

[FLAG] Here is your flag:
[FLAG] pwn.college{8Yf8B7BG-pPMPRD5tl8U836ZeT8.dVjN1QDL4ADO0czW}
 
 # Appending output

 Command line:

 `
 hacker@piping~appending-output:~$ /challenge/run >> /home/hacker/the-flag
 `
 
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

`
hacker@piping~appending-output:~$ cat the-flag
 `
 
     |

    \|/ This is the first half:

     v

`pwn.college{4axyHazp7JFALCRbQ9mBbrJrUHM.ddDM5QDL4ADO0czW} `

                              ^
     that is the second half /|\
                              |

If you only see the second half above, you redirected in *truncate* mode (>)
rather than *append* mode (>>), and so the write of the second half to stdout
overwrote the initial write of the first half directly to the file. Try append
mode!

# Redirecting input

Command line:

`
hacker@piping~redirecting-input:~$ /challenge/run < PWN
`

Reading from standard input...
Correct! You have redirected the PWN file into my standard input, and I read
the value 'COLLEGE' out of it!

`
Here is your flag:
pwn.college{UjNftJtc2n_4SzA9w9m_IZpcUiL.dBzN1QDL4ADO0czW}
`

# Grepping live output

Command line:

`
hacker@piping~grepping-stored-results:~$ /challenge/run > /tmp/data.txt
`

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

`
hacker@piping~grepping-stored-results:~$ grep pwn /tmp/data.
txt
`

pwning

pwn

pwned

pwn.college{YaOtgkX87fOz2YSuh4wpiPmZtSs.dhTM4QDL4ADO0czW}

pwns

# Grepping live output

Command line:

`
hacker@piping~grepping-live-output:~$ /challenge/run | grep pwn.college
`

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

`
pwn.college{gFye0oW0xfZ4BuY23_VChC_5ryZ.dlTM4QDL4ADO0czW}
`

# Grepping errors

Command line:

`
hacker@piping~grepping-errors:~$ /challenge/run 2>&1 |grep pwn.college
`

[INFO] WELCOME! This challenge makes the following asks of you:

[INFO] - the challenge checks for a specific process at the other end of stderr : grep

[INFO] - the challenge will output a reward file if all the tests pass : /challenge/.data.txt

[HYPE] ONWARDS TO GREATNESS!

[INFO] This challenge will perform a bunch of checks.

[INFO] If you pass these checks, you will receive the /challenge/.data.txt file.

[TEST] You should have redirected my stderr to another process. Checking...

[TEST] Performing checks on that process!

[INFO] The process' executable is /nix/store/xpq4yhadyhazkcsggmqd7rsgvxb3kjy4-gnugrep-3.11/bin/grep.

[INFO] This might be different than expected because of symbolic links (for example, from /usr/bin/python/usr/bin/python3 to /usr/bin/python3.8).

[INFO] To pass the checks, the executable must be grep.

[PASS] You have passed the checks on the process on the other end of my stderr!

[PASS] Success! You have satisfied all execution requirements.

`
pwn.college{Y7b82Dmx41vsmpFF25amUmvN5IR.dVDM5QDL4ADO0czW}
`

# Spli-piping stderr and stdout

Command line:

`
hacker@piping~split-piping-stderr-and-stdout:~$ /challenge/hack 2> >(/challenge/the) | /challenge/planet
`
Congratulations, you have learned a redirection technique that even experts
struggle with! Here is your flag:

`
pwn.college{svPqJkgj9LAiKzuZGwZS3P3bsYo.dFDNwYDL4ADO0czW}
`
