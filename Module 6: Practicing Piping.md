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
 # 
 
