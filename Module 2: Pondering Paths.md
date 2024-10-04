# 1.The Root:
In this challenge a program was already in **/** and named as pwn so I had to use it’s absolute path **/pwn** to get the flag.
# 2.Program and Absolute paths:
In this challenge I had to execute the command run in the directory ‘**challenge**’ which was in the root directory. So my absolute path is  /challenge/run to get the flag.
# 3.Position thy self:
We can navigate around directories by using the cd (change directory) command and passing a path to it as an argument
Also the   ~   shows the current location of the shell
Here we had to execute the program /challenge/run from a specific path (which we would obtain after entering the wrong path) and after getting the right we get the flag
# 4.Position elsewhere:
Same as challenge 3.Positon thy self
# 5.Position yet elsewhere:
Same as challenge 3.Positon thy self
# 6.Implicit relative paths, from /
Here they talk about relative paths and how it does not start at root and how it is based on your current location(or current working directory cwd).

So to complete the challenge we start from / directory and use the relative path to execute the program is challenge/run.
# 7.Explicit relative paths from /: 
Here they talk about using "." and ".." in Relative Paths, where “.”  is the current directory and “..” is the parent directory.

To complete the challenge we change directory(cd) to root / and execute  ./challenge/run to get the flag.
# 8.Implicit relative path:
Here they talk about Linux explicitly avoiding automatically looking in the current directory when you provide a "naked" path.  This happens to be a safety measure , for if we accidentally execute programs in your current directory that happened to have the same name.

To get the flag we start from the absolute path /challenge and to launch run we use the relative path ./run. 
# 9.Home sweet home:
When you log in, the tilde (~) in the prompt shows your home directory (/home/hacker in this case). You can use ~ as a shortcut when specifying file paths within your home directory
So to complete the challenge with these constraints:
1.	Your argument must be an absolute path.
2.	The path must be inside your home directory.
3.	Before expansion, your argument must be three characters or less.
	
Then the command will be /challenge/run and the argument will be ~/a( I used a here but you can use any character). 
        
