# Becoming root with su 

Commmand line:

`hacker@users~becoming-root-with-su:~$ su`

Password: hack-the-planet

`root@users~becoming-root-with-su:/home/hacker# cat /flag`

pwn.college{ovMp6pFAIcMcmcIRuoCBk778iWq.dVTN0UDL4ADO0czW}

# Other users with su

Command line:

`hacker@users~other-users-with-su:~$ su zardus`

Password: dont-hack-me

`zardus@users~other-users-with-su:/home/hacker$ /challenge/run`

Congratulations, you have become Zardus! Here is your flag:

pwn.college{0BjsIwlh97hJpdCtF33KlARqDxC.dZTN0UDL4ADO0czW}

# Cracking passwords

Command line:

`hacker@users~cracking-passwords:~$ john /challenge/shadow-leak`

Loaded 1 password hash (crypt, generic crypt(3) [?/64])

Press 'q' or Ctrl-C to abort, almost any other key for status

0g 0:00:00:08 82% 1/3 0g/s 273.6p/s 273.6c/s 273.6C/s zardus111..Z999990000

aardvark         (zardus)

1g 0:00:00:21 100% 2/3 0.04629g/s 269.5p/s 269.5c/s 269.5C/s Johnson..buzz

Use the "--show" option to display all of the cracked passwords reliably

Session completed

`hacker@users~cracking-passwords:~$ su zardus`

Password:

`zardus@users~cracking-passwords:/home/hacker$ /challenge/run`

Congratulations, you have become Zardus! Here is your flag:

pwn.college{8oz8yI6McrAfgeJ2ok4hfVe2fmG.ddTN0UDL4ADO0czW}

# Using sudo

Command line:

`hacker@users~using-sudo:~$ sudo cat /flag`
pwn.college{olphoMLSY1jonNZcM8IAVN8f8YO.dhTN0UDL4ADO0czW}
