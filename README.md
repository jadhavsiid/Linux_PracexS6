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
**Program-4:  Write shell script to execute switch and if else loop.**
``` console

# if-else statement
echo "Executing if-else Statement"

echo "Enter your age: "
read age
if [ $age -gt 18 ]
 then
  echo "You're Eligible to Drive."
else
  echo "You aren't yet Eligible to Drive."
fi

echo ""

# Swith Statement
echo "Executing Switch Statement"

echo "Enter name of any fruit"
read fruit
case "$fruit" in
  "apple") echo "This is an apple.";;
  "banana") echo "This is an banana.";;
  "orange") echo "This is an orange.";;
    *) echo "I Don't Know what fruit this is.";;
esac
```
**Program-5: . Write a shell script to show various system configuration like currently logged user and 
his logname, your current shell, home directory, operating system type, current path 
setting, current working directory, show currently logged number of users, show 
memory information, Hard disk information like size of hard-disk, cache model etc, and 
file system mounted.**

``` console
#!/bin/bash

# Various System Configurations

# Current Logged user
echo ""
echo "Current Logged User: $USER"
echo ""
# Show Current Shell
echo "Current Shell: $SHELL"
echo ""
# Show Home Directory
echo "Home Directory: $HOME"
echo ""
# Show Operating System
echo "Operating System: $(uname -o)"
echo ""
# Current Path Setting
echo "Current Path Setting: $PATH"
echo ""
# Current Working Directroy
echo "Current Working Directory: $(pwd)"
echo ""
# Memory Information
echo "Memory Information:"
free -m
echo ""
# Hard Disk Info
echo "Hard Disk Info:"
df -h
echo""
# Cache Model
echo "Cache Model:"
lscpu | grep "L3 cache"
echo ""
# File System Mounted
echo "File System Mounted:"
mount | column -t
echo""
```

**Program-6: Write a shell script to add user and password on Linux system.**
``` console
#!/bin/bash

# Script to add user and password on Linux system

# Ask for user details
read -p "Enter username: " username
read -s -p "Enter password: " password
echo

# Check if user already exists
if id "$username" &>/dev/null; then
    echo "User already exists. Aborting."
    exit 1
fi

# Add user
sudo useradd -m -s /bin/bash "$username"

# Set password for user
echo "$username:$password" | sudo chpasswd

# Display message
echo "User '$username' added successfully with password '$password'."
```

**Program-7:  Write a shell script that delete all lines containing a specified word.**

``` console
#!/bin/bash

# Write a shell script that deletes all lines containing a specified word.

echo "Enter file name:"
read file
echo ""
echo "Enter specific word from the file:"
read word
echo ""
echo "File before removing word \"$word\":"
cat $file
grep -v -i "$word" "$file" > test
mv test "$file"
echo ""
echo "File after removing word \"$word\":"
cat $file
```

**Program-8:   Write a shell script to upgrade and cleans the system automatically instead of doing it manually.**

``` console
#!/bin/bash

# Write a shell script to upgrade and cleans the system automatically instead of doing it manually

# Update system packages
sudo apt update && sudo apt upgrade -y

# Clean system packages
sudo apt autoremove -y && sudo apt autoclean

```
