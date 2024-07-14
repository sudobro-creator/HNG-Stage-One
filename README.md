# Linux User Creation Bash Script
<h3>HNG-Stage-One</h3>

# Overview
This project provides a Bash script, create_users.sh, designed to automate the creation of users and groups on a Linux system. This script is particularly useful for SysOps engineers responsible for managing large numbers of user accounts.  Additionally, it stores the generated passwords securely giving only the file owner a read and write permission. 

# Requirements
- Each user must have a personal group with the same group name as the username (this group name will not be written in the text file).
- A user can have multiple groups, each group delimited by a comma ,.
- Usernames and user groups are separated by a semicolon ;.
- Ignore whitespace.


# Objectives
The Bash script `create_users.sh` reads the text file containing the employee’s usernames and group names. Each line in the file is formatted as user;groups. 
```
light; sudo,dev,www-data
idimma; sudo
mayowa; dev,www-data
```
The script should perform the following tasks:
- Create users and groups as specified
- Set up home directories with appropriate permissions and ownership
- Generate random passwords for the users
- Log all actions to `/var/log/user_management.log`
- Store the generated passwords securely in `/var/secure/user_passwords.txt`
- Perform error handling for scenarios like existing users



# Usage
- To run the script, use the following command:
```
bash create_users.sh <name-of-text-file>
```
- To check for logs, run this:
```
/var/log/user_management.log
```
This file should contain a log of all actions performed by the script.
<br>
```
/var/secure/user_passwords.txt
```
This file should contain a list of all users and their passwords, delimited by a comma, and only the file owner should be able to read it. 
Use this command to ensuer only the file owner can read it
```
chmod 600 /var/secure/user_passwords.txt
```

# Dev.to
For more detailed walkthrough, check out <a href="https://dev.to/sudobro/automating-creation-of-users-and-groups-using-bash-script-step-by-step-guide-3dm0">my article</a>
