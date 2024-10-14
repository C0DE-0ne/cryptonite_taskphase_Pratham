# Printing variables
So to get the flag we print out the variable using the command echo.
Command line:

`hacker@variables~printing-variables:~$ echo FLAG`

FLAG

`hacker@variables~printing-variables:~$ echo $FLAG`

pwn.college{QyUBWKPaI_dxLKBKI5BKTOHp2AO.ddTN1QDL4ADO0czW}

# Setting variables
Here we give the variable a value using =. To get the flag we assign the variable PWN the value COLLEGE

Command line:

`hacker@variables~setting-variables:~$ PWN=COLLEGE`

You've set the PWN variable properly! As promised, here is the flag:

pwn.college{438vtTAD46tMde9rBssbV3SoEgE.dlTN1QDL4ADO0czW}

#Multi-word variables
We learn that if we want to put a value with space in it we have use " ".

Command line:

`hacker@variables~multi-word-variables:~$ PWN="COLLEGE YEAH"`

You've set the PWN variable properly! As promised, here is the flag:

pwn.college{YV9-yi6S9S_IrlxMVe0RKBei7SC.dBjN1QDL4ADO0czW}

# Exporting variables

Command line:

`hacker@variables~exporting-variables:~$ export PWN=COLLEGE`

You've set the PWN variable to the proper value!

`hacker@variables~exporting-variables:~$ COLLEGE=PWN`

You've set the PWN variable to the proper value!

You've set the COLLEGE variable to the proper value!

`hacker@variables~exporting-variables:~$ /challenge/run`

CORRECT!

You have exported PWN=COLLEGE and set, but not exported, COLLEGE=PWN. Great
job! Here is your flag:

pwn.college{4uOiZOXcY0Gt7zKEWaIlL8895yQ.dJjN1QDL4ADO0czW}

You've set the PWN variable to the proper value!

You've set the COLLEGE variable to the proper value!

# Printing exported variables


# Storing command output
To store the output of a command into a variable we usse command substitution.

Command line:

`hacker@variables~storing-command-output:~$ PWN=$(/challenge/run /flag)`

Congratulations! You have read the flag into the PWN variable. Now print it out
and submit it!

`hacker@variables~storing-command-output:~$ echo "$PWN"`

pwn.college{gkuf-hzovFL_QjrM7xM8F3psKis.dVzN0UDL4ADO0czW}

# Reading input

Command line:

`hacker@variables~reading-input:~$ read -p "INPUT: " PWN`

INPUT: COLLEGE

You've set the PWN variable properly! As promised, here is the flag:

pwn.college{ELE3_CcxBxO9a8qhpOt_9hIAhXb.dhzN1QDL4ADO0czW}

# Reading files
The read builtin, reads the input. So using `read -p` we can can give values to variables. To get the flag the variable PWN is to be set with value COLLEGE.

Command line:

`hacker@variables~reading-input:~$ read -p "INPUT: " PWN`

INPUT: COLLEGE

You've set the PWN variable properly! As promised, here is the flag:

pwn.college{ELE3_CcxBxO9a8qhpOt_9hIAhXb.dhzN1QDL4ADO0czW}

# Reading files

Command line:

`hacker@variables~reading-files:~$ read PWN < /challenge/read_me`

You've set the PWN variable properly! As promised, here is the flag:

pwn.college{EjZB7cIca2xGyxgosYSnefBKPwN.dBjM4QDL4ADO0czW}
