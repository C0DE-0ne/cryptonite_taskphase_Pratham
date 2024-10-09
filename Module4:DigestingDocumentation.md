# 1.Learning from documentation
Here a documentation was given about the program /challenge/run, so to get the flag we had to run it with the arguement --giveflag

Command line:

``
hacker@man~learning-from-documentation:~$ /challenge/challenge --giveflag
Correct argument! Here is your flag:
pwn.college{QmkwPXP7fsF8-VJ0MeYsWnNmeLO.dRjM5QDL4ADO0czW} 
``

# 2.Learning complex Usage

Command line:

``
hacker@man~learning-complex-usage:~$ /challenge/challenge --printfile /flag
Correct argument! Here is the /flag file:
pwn.college{MM6BFBU2U53QTX13LcDY8adIdb6.dVjM5QDL4ADO0czW}
``

# 3.Reading Manuals

 Command line:

 ``
 hacker@man~reading-manuals:~$ man challenge

CHALLENGE(1)        Challenge Commands        CHALLENGE(1)

NAME
       /challenge/challenge - print the flag!

SYNOPSIS
       challenge OPTION

DESCRIPTION
       Output  the  flag  when called with the right argu‐
       ments.

       --fortune
              read a fortune

       --version
              output version information and exit

       --cbwgep NUM
              print the flag if NUM is 602

AUTHOR
       Written by Zardus.

REPORTING BUGS
       The      repository      for       this       dojo:
       <https://github.com/pwncollege/linux-luminarium/>

SEE ALSO
       man(1) bash-builtins(7)

pwn.college              May 2024             CHALLENGE(1)
hacker@man~reading-manuals:~$ /challenge/challenge --cbwgep 602
Correct usage! Your flag: pwn.college{cbwg-eGP6pOMO0i29brdJ5yQa9Z.dRTM4QDL4ADO0czW}
``

# 4.Searching for manuals

Command line:

``
. hacker@man~searching-manuals:~$ man challenge
hacker@man~searching-manuals:~$ /challenge/challenge --beyggg
Initializing...
Correct usage! Your flag: pwn.college{AlRopeL8CNn606a7b0iKOxpuszc.dVTM4QDL4ADO0czW}
``

# 5.Searching for Manual

Command line:

`
hacker@man~searching-for-manuals:~$ man qkkgpyqtxd

CHALLENGE(1)        Challenge Commands        CHALLENGE(1)

NAME
       /challenge/challenge - print the flag!

SYNOPSIS
       challenge OPTION

DESCRIPTION
       Output  the  flag  when called with the right argu‐
       ments.

       --fortune
              read a fortune

       --version
              output version information and exit

       --qkkgpy NUM
              print the flag if NUM is 340

AUTHOR
       Written by Zardus.

REPORTING BUGS
       The      repository      for       this       dojo:
       <https://github.com/pwncollege/linux-luminarium/>

SEE ALSO
       man(1) bash-builtins(7)

pwn.college              May 2024             CHALLENGE(1)
hacker@man~searching-for-manuals:~$ /challenge/challenge --qkkgpy 340
Correct usage! Your flag: pwn.college{I_IH34-Q_q_k0kgSpNTYyqtQ-xP.dZTM4QDL4ADO0czW}
`

# 6.Helpful programs

Command line:

`
hacker@man~helpful-programs:~$ /challenge/challenge -h
hacker@man~helpful-programs:~$ /challenge/challenge -p
The secret value is: 827
hacker@man~helpful-programs:~$ /challenge/challenge -g827
Correct usage! Your flag: pwn.college{YvozxFdI8CmecKWONuSSb2dJA71.ddjM4QDL4ADO0czW}
`

# 7.Help for builtins

Command line:

`
hacker@man~help-for-builtins:~$ help challenge
challenge: challenge [--fortune] [--version] [--secret SECRET]
    This builtin command will read you the flag, given the right arguments!
    You must be sure to provide the right value to --secret. That value
    is "ASHDMX8n".
hacker@man~help-for-builtins:~$ challenge --secret ASHDMX8n
Correct! Here is your flag!
pwn.college{ASHDMX8nEA-ceGHx6sOaAKdaZad.dRTM5QDL4ADO0czW}
`
