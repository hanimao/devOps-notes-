
==File==

Human readable file

- file ./*

Finding a file when there is multiple directories. 

- find . -readable -size 1033c ! -executable
! = not
. = current directory 
c = bytes 

==**Directories**==
Creating directories 

- mkdir project

Create multiple directories

- mkdir -p project/src/components

To see the directories

- ls -R project (the -R list directories recursively)

Remove **empty** directories

- rmdir project/src/components 

Remove directories and **all its contents**

- rm -r project

Dealing with Spaces in Folder Names

Either
- mkdir "My Project"
- mkdir My\ Project\ 2

==**Vim Editor**==
How to open a file 

vim example.txt  - (vim will create a new file if it does not exit)

**==Sudo Command==** 
allows a permitted user to execute a command as the super/root user

- installing a package
- updating a package 
- editing system file - configuration file in etc

The root user + a very dangerous command!

rm -rf /

removes everything in the Linux machine...

==Users==
- sudo useradd newuser
- sudo passwd newuser 

Log in
- su - newuser
(substitute user)

Give users sudo privileges(adding newuser to the root group)
- sudo usermod -aG sudo newuser

==Groups==
Create a group
- sudo groupadd devops
Delete a group
- sudo groupdel devops 

Remove user from a group
- sudo gpasswd -d newuser group
To check if the group exists
- grep devops /etc/group

==File Permission==
- File permission is represented as rwx but they can also be represented as the binary, octal and string format.
- The binary format is represented as binary digits. It is a set of digits represented by 0 and 1.
- The octal is a compact representation using numbers. 
 To set file permission using the command line use the octal notation
 To make it easier, there are online tools available that can convert these permission for you. The chmod calculator is a tool that help you visualize and calculate the correct notation quickly. 
 symbolic file permission rwx uses these letters to represent the permissions for the user, group and others. 
- chmod u+x, g+r,o-w file.txt
- chmod 600 

The chmod command allows you to change the permissions of a file or a directory. There are 2 ways to use chmod, symbolic or numeric. 



Script are executable file that can be run as a program.
Executing a file
- ./filename

Grouping permissions using symbolic operators
- chmod ug=rw, o=r filename.txt

==Changing File/Directory ownership==

File
- sudo chown username file.txt
Group
- sudo chgrp groupname file.txt

- sudo chown user:group filename.txt

Directory 

- sudo chown -R user:group filename.txt

==Standard Streams== 

1. Standard input/stdin
This is the stream that provides input to commands.
When you write something and this is passed into the running program.
2. Standard output/stdout
Displayed on the terminal screen. 
3. Standard error/stderr
Used for sending error messages

