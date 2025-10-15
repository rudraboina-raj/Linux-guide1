# Linux-guide1
Linux commands in detail

 1. User Management in Linux

Introduction to User Management in Linux
Linux is a multi-user operating system, meaning multiple users can operate on a system simultaneously. Proper user management ensures security, controlled access, and system integrity.

Key files involved in user management:

/etc/passwd – Stores user account details.
/etc/shadow – Stores encrypted user passwords.
/etc/group – Stores group information.
/etc/gshadow – Stores secure group details.
Creating Users in Linux
To create a new user in Linux, use:

useradd Command (For most Linux distributions)
useradd username
This creates a user without a home directory.

To create a user with a home directory:

useradd -m username
To specify a shell:

useradd -s /bin/bash username
adduser Command (For Debian-based systems)
adduser username
This is an interactive command that asks for a password and additional details.

Managing User Passwords
To set or change a user’s password:

passwd username
Enforcing Password Policies
Password expiration: Set password expiry days
chage -M 90 username
Lock a user account
passwd -l username
Unlock a user account
passwd -u username
Modifying Users
Modify an existing user with usermod:

Change the username:
usermod -l new_username old_username
Change the home directory:
usermod -d /new/home/directory -m username
Change the default shell:
usermod -s /bin/zsh username
Deleting Users
To remove a user but keep their home directory:

userdel username
To remove a user and their home directory:

userdel -r username
Working with Groups
Creating Groups
groupadd groupname
Adding Users to Groups
usermod -aG groupname username
Viewing Group Memberships
groups username
Changing Primary Group
usermod -g new_primary_group username
Sudo Access and Privilege Escalation
Adding a User to Sudo Group
On Debian-based systems:

usermod -aG sudo username
On RHEL-based systems:

usermod -aG wheel username
Granting Specific Commands with Sudo
Edit the sudoers file:

visudo
Then add:

username ALL=(ALL) NOPASSWD: /path/to/command

 2. File management in Linux
 
File and Directory Management
ls – Lists files and directories in the current location.
cd /path/to/directory – Changes the working directory.
pwd – Prints the current working directory.
mkdir new_folder – Creates a new directory.
rmdir empty_folder – Removes an empty directory.
rm file.txt – Deletes a file.
rm -r folder – Deletes a folder and its contents.
cp file1.txt file2.txt – Copies a file.
cp -r dir1 dir2 – Copies a directory recursively.
mv old_name new_name – Moves or renames a file or directory.
File Viewing and Editing
cat file.txt – Displays file content.
tac file.txt – Displays file content in reverse order.
less file.txt – Opens a file for viewing with scrolling support.
more file.txt – Similar to less, but only moves forward.
head -n 10 file.txt – Displays the first 10 lines of a file.
tail -n 10 file.txt – Displays the last 10 lines of a file.
nano file.txt – Opens a simple text editor.
vi file.txt – Opens a powerful text editor.
echo 'Hello' > file.txt – Writes text to a file, overwriting existing content.
echo 'Hello' >> file.txt – Appends text to a file without overwriting.