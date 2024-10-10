# Matching with *
Glob * lets you match pattern When it encounters a * character in any argument, the shell will treat it as "wildcard" and try to replace that argument with any files that match the pattern. When zero files are matched, by default, the shell leaves the glob unchanged

Command line:

`
hacker@globbing~matching-with-:~$ cd /c*
hacker@globbing~matching-with-:/challenge$ /challenge/run
You ran me with the working directory of /challenge! Here is your flag:
pwn.college{sBmK57DvXDCku63Ji7_RigoeyZ3.dFjM4QDL4ADO0czW}
`

# Matching with ?
It works like * but only matche single character cd /?ha??enge to get the flag.

Command line:

`
This challenge resets your working directory to /home/hacker unless you change
directory properly...
hacker@globbing~matching-with-:~$ cd /?ha??enge
hacker@globbing~matching-with-:/challenge$ /challenge/run
You ran me with the working directory of /challenge! Here is your flag:
pwn.college{odgDFqGaE70EGZDZFh3SZCJaD4l.dJjM4QDL4ADO0czW}
`

# Matchimg with []
So here we have to put the potential characters to match with file in the bracket.

Command line:

`
hacker@globbing~matching-with-:~$ cd /challenge/files
hacker@globbing~matching-with-:/challenge/files$ /challenge/run file_[absh]
You got it! Here is your flag!
pwn.college{YPjXtbLpHIFYSva2xiYVvK3Z401.dNjM4QDL4ADO0czW}
`

# Matching paths with []
Here it is same as before but we specify path of the files and glob in the path.

Command line:

`
hacker@globbing~matching-paths-with-:~$ /challenge/run /challenge/files/file_[bash]
You got it! Here is your flag!
pwn.college{keuYzC_zTQSKKfF7STJi2E1swJu.dRjM4QDL4ADO0czW}
`

# Mixing globs
So to get the flag here cd to /challenege/files for globbing files challenge,education and pwning. Use [] to match and * for the remaining characters.

Command line:

`
hacker@globbing~mixing-globs:~$ cd /challenge/files
hacker@globbing~mixing-globs:/challenge/files$ /challenge/run [cep]*
You got it! Here is your flag!
pwn.college{YYKxe5cqcuYA-ZTqA8bt0qAO1hp.dVjM4QDL4ADO0czW}
`

# Exclusionary Globbing
So if the first character is ! or ^ ,the glob inverts ,and the bracket instead matches characters that that don't start with given character.

Command line:

`
hacker@globbing~exclusionary-globbing:~$ cd /challenge/files
hacker@globbing~exclusionary-globbing:/challenge/files$ /challenge/run [^pwn]*
You got it! Here is your flag!
pwn.college{sRmFoAGjWOfIG5S7d609Wbk9Kvt.dZjM4QDL4ADO0czW}
`
