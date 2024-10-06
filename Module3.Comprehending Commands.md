# 1.Cat: not the pet, but the command #
Here they talk about cat, a command used to read out files. So to get the flag 

Command line

hacker@commands~cat-not-the-pet-but-the-command:~$ cat flag

pwn.college

# 2.catting absolute paths #
Here we use cat command with an absolute path as its argument.

Command line:

hacker@commands~catting-absolute-paths:~$ cat /flag

pwn.college

# 3.more catting practice #
We can’t  cd into the directory so we must us the given path as the argument to the flag.

Command line:

must retrieve the flag by
absolute path. Plus, I hid the flag in a different directory! You can find it
in the file /usr/include/bsd/flag. Go cat it out **without** cding into that
directory!

hacker@commands~more-catting-practice:~$ cat /usr/include/bsd/flag

pwn.college

# 4.grepping for a needle in a haystack #
The grep command is use to find lines with specific text

Command line:

hacker@commands~grepping-for-a-needle-in-a-haystack:~$ grep pwn.college /challenge/data.txt

pwn.college

# 5.listing files
Ok so ls command lists the files in a directory 

Command line:

hacker@commands~listing-files:~$ ls /challenge

5977-renamed-run-368      DESCRIPTION.md
hacker@commands~listing-files:~$ /challenge/5977-renamed-run-368

Yahaha, you found me! Here is your flag:

pwn.college
# 6.touching files
 You can create a new, blank file by touching it with the touch command. To get the flag create two files.

Command line:
hacker@commands~touching-files:~$ cd /tmp
hacker@commands~touching-files:/tmp$ touch pwn
hacker@commands~touching-files:/tmp$ touch college
hacker@commands~touching-files:/tmp$ ls
bin  college  hsperfdata_root  pwn  tmp.G9qthVCks5
hacker@commands~touching-files:/tmp$ /challenge/run

Success!

Here is your flag:

pwn.college

# 7.removing files
It’s simple, the rm command removes a file

Command line:

hacker@commands~removing-files:~$ ls
a  asdf  delete_me
hacker@commands~removing-files:~$ rm delete_me
hacker@commands~removing-files:~$ ls
a  asdf
hacker@commands~removing-files:~$ /challenge/check
Excellent removal. Here is your reward:

pwn.college

# 8.hidden files
Well well, so we can some hid files using  .  but still we can view it by using ls -a 

Command line:

hacker@commands~hidden-files:~$ cd /

hacker@commands~hidden-files:/$ ls

bin        dev   lib    libx32  nix   root  srv  usr

boot       etc   lib32  media   opt   run   sys  var

challenge  home  lib64  mnt     proc  sbin  tmp

hacker@commands~hidden-files:/$ ls -a

.                      boot       lib     mnt   run   usr

..                     challenge  lib32   nix   sbin  var

.dockerenv             dev        lib64   opt   srv

.flag-309651189113705  etc        libx32  proc  sys

bin                    home       media   root  tmp

hacker@commands~hidden-files:/$ cat .flag-309651189113705

pwn.college

# 9.an epic filesystem quest
All the commands learnt before this were put to the test.
(Didn't feel like putting in all that code and also i forgot to copy it before moving on.)

# 10.making directories
Now we can create directories using the mkdir command 

Command line:

hacker@commands~making-directories:~$ ls

a  asdf

hacker@commands~making-directories:~$ cd /

hacker@commands~making-directories:/$ ls

bin        dev   home   lib64   mnt  proc  sbin  tmp

boot       etc   lib    libx32  nix  root  srv   usr

challenge  flag  lib32  media   opt  run   sys   var

hacker@commands~making-directories:/$ cd tmp

hacker@commands~making-directories:/tmp$ ls

bin  hsperfdata_root  tmp.G9qthVCks5

hacker@commands~making-directories:/tmp$ mkdir pwn

hacker@commands~making-directories:/tmp$ ls

bin  hsperfdata_root  pwn  tmp.G9qthVCks5

hacker@commands~making-directories:/tmp$ cd pwn

hacker@commands~making-directories:/tmp/pwn$ ls

hacker@commands~making-directories:/tmp/pwn$ touch college

hacker@commands~making-directories:/tmp/pwn$ ls

college
hacker@commands~making-directories:/tmp/pwn$ /challenge/run


Success! 

Here is your flag:

pwn.college

# 11.finding files
The challenge statement instructs us to find a file flag which is in some random directory in the filesystem. This can be done by using the find command
(but still I got it on the first time hahaha)
Command lines:
hacker@commands~finding-files:~$ find -name flag

hacker@commands~finding-files:~$ find / -name flag

find: ‘/root’: Permission denied
find: ‘/etc/ssl/private’: Permission denied
find: ‘/tmp/tmp.G9qthVCks5’: Permission denied
/usr/local/share/radare2/5.9.5/flag
/usr/local/lib/python3.8/dist-packages/pwnlib/flag
/usr/share/doc/libsodium23/flag
find: ‘/var/cache/apt/archives/partial’: Permission denied
find: ‘/var/cache/ldconfig’: Permission denied
find: ‘/var/cache/private’: Permission denied
find: ‘/var/log/private’: Permission denied
find: ‘/var/log/apache2’: Permission denied
find: ‘/var/log/mysql’: Permission denied
find: ‘/var/lib/apt/lists/partial’: Permission denied
find: ‘/var/lib/mysql-keyring’: Permission denied
find: ‘/var/lib/php/sessions’: Permission denied
find: ‘/var/lib/private’: Permission denied
find: ‘/var/lib/mysql-files’: Permission denied
find: ‘/var/lib/mysql’: Permission denied
find: ‘/run/mysqld’: Permission denied
find: ‘/run/sudo’: Permission denied
find: ‘/proc/tty/driver’: Permission denied
find: ‘/proc/1/task/1/fd’: Permission denied
find: ‘/proc/1/task/1/fdinfo’: Permission denied
find: ‘/proc/1/task/1/ns’: Permission denied
find: ‘/proc/1/fd’: Permission denied
find: ‘/proc/1/map_files’: Permission denied
find: ‘/proc/1/fdinfo’: Permission denied
find: ‘/proc/1/ns’: Permission denied
find: ‘/proc/7/task/7/fd’: Permission denied
find: ‘/proc/7/task/7/fdinfo’: Permission denied
find: ‘/proc/7/task/7/ns’: Permission denied
find: ‘/proc/7/fd’: Permission denied
find: ‘/proc/7/map_files’: Permission denied
find: ‘/proc/7/fdinfo’: Permission denied
find: ‘/proc/7/ns’: Permission denied
/opt/pwndbg/.venv/lib/python3.8/site-packages/pwnlib/flag
/opt/radare2/libr/flag
/nix/store/pmvk2bk4p550w182rjfm529kfqddnvh3-python3.11-pwntools-4.12.0/lib/python3.11/site-packages/pwnlib/flag
/nix/store/1yagn5s8sf7kcs2hkccgf8d0wxlrv5sz-radare2-5.9.0/share/radare2/5.9.0/flag

hacker@commands~finding-files:~$ cat /usr/share/doc/libsodium23/flag

pwn.college
# 12.Linking files
Solt links can be created using ln -s 
The challenge statement asks us to get /flag by executing /challenge/catflag however, /challenge/catflag will read out /home/hacker/not-the-flag.
We can trick the /challenge/catflag file to give us the flag if we successfuly symlink not-the-flag file to /flag file

Command line:

hacker@commandslinking-fles:$ In-s /flag/home/hacker/not-the-flag 

hacker@commandslinking-fles:$ /challenge/catflag.

About to read out the /home/hacker/not-the-flag file! 

pwn.college
