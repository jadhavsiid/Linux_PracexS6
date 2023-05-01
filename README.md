# Linux Practical Exam (Sem-6)
A repository for all the programs which would be asked in a practical Linux Practical Exam Sem-6.

**Program-1: To execute basic Linux commands**

1.) <b> ls: </b> The ls command is used to list files and directories in the current working directory.
```console
unix@SIDDELL2018:~$ ls
```
2.) <b> cd: </b> Changes the current working directory.
```console
unix@SIDDELL2018:~$ cd
```
3.) <b> pwd: </b> Print's Working Directory.
```console
unix@SIDDELL2018:~$ pwd
```
4.) <b> mkdir: </b> Makes Directory.
```console
unix@SIDDELL2018:~$ mkdir newdir
```
5.) <b> rmdir: </b> Removes Directory.
```console
unix@SIDDELL2018:~$ rmdir newdir
```
6.) <b> cd: </b> Changes the current working directory.
```console
unix@SIDDELL2018:~$ cd
```
7.) <b> touch: </b> Creates an empty file in an working directory
```console
unix@SIDDELL2018:~$ touch newfile
```
8.) <b> nano: </b> used to acces a file made in a working directory
```console
unix@SIDDELL2018:~$ nano newfile
```
9.) <b> bash: </b> used to run programs written in bash file (files with .sh extension)
```console
unix@SIDDELL2018:~$ bash newfile
```
**Program-2: Write shell script to execute for and if loop.**

Make New file first by typing **nano forandif.sh**

Program:
``` console
#!/bin/bash

#Write shell script to execute for and if loop.

num=(1 2 3 4)
for number in ${num[@]}
do
if (( $number % 2 == 0 ))
 then
  echo "$number is even"
else
  echo "$number is Odd"
fi
done
```
execute the program using **bash forandif.sh**

**Program-3:  Write shell script to execute until and while loop.**

Program:
``` console
#!/bin/bash
# Write shell script to execute until and while loop.

# Executing until
counter=1
echo "Executing until"
until [ $counter -gt 5 ]
do
 echo "The Value of Counter is: $counter"
 counter=$((counter+1))
done

# Executing while
counter2=1
echo "Executing While"
until [ $counter2 -ge 5 ]
do
 echo "The value of Counter is: $counter2"
 counter2=$((counter2+1))
done
```
