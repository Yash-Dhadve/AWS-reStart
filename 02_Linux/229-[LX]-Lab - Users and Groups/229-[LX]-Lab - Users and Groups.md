Managing Users and Groups Lab Walkthrough

Aim:
To create users and groups in Linux, assign users to appropriate groups, verify group memberships, and understand sudo privileges and user switching.

Requirements:
• AWS Academy Lab Environment
• Amazon Linux EC2 Instance
• SSH Access (PuTTY or Terminal)

Procedure:w

Task 1: Connect to the EC2 Instance

1. Started the lab and waited until the lab status became "Ready".
2. Opened the AWS Management Console.
3. Downloaded the SSH key file (PPK or PEM).
4. Noted the Public IP address of the EC2 instance.
5. Connected to the EC2 instance using SSH.

For macOS/Linux:

Command:
ssh -i labsuser.pem ec2-user@<Public-IP>

Observation:
Successfully logged in as ec2-user.

Task 2: Create Users

1. Verified the current working directory.

Command:
pwd

Output:
/home/ec2-user

2. Created user accounts using the useradd command.

Example:
sudo useradd arosalez

3. Assigned passwords to the users.

Example:
sudo passwd arosalez

Password Used:
P@ssword1234!

4. Repeated the process for all users listed below:

User IDs:
arosalez
eowusu
jdoe
ljuan
mmajor
mjackson
nwolf
psantos
smartinez
ssarkar

5. Verified user creation.

Command:
sudo cat /etc/passwd | cut -d: -f1

Observation:
All newly created users appeared in the list.

Task 3: Create Groups

1. Created the required groups using the groupadd command.

Groups Created:
Sales
HR
Finance
Shipping
Managers
CEO

Example:
sudo groupadd Sales

2. Verified group creation.

Command:
cat /etc/group

Observation:
The newly created groups appeared in the output.

3. Added users to their respective groups.

Group Memberships:

Sales:
arosalez
nwolf

HR:
ljuan
smartinez

Finance:
mmajor
ssarkar

Shipping:
eowusu
jdoe
psantos

Managers:
arosalez
ljuan
mmajor

CEO:
mjackson

4. Added ec2-user to all groups.

5. Verified memberships.

Command:
sudo cat /etc/group

Observation:
All users appeared under the correct groups.

Task 4: Test User Login and Sudo Access

1. Switched to another user.

Command:
su arosalez

Password:
P@ssword1234!

2. Verified the current directory.

Command:
pwd

Output:
/home/ec2-user

3. Attempted to create a file.

Command:
touch myFile.txt

Observation:
Permission denied error occurred because arosalez did not have write access to the ec2-user home directory.

4. Attempted to use sudo.

Command:
sudo touch myFile.txt

Observation:
Received the message:

"arosalez is not in the sudoers file."

This confirmed that normal users cannot execute administrative commands using sudo.

5. Returned to ec2-user.

Command:
exit

6. Viewed the secure log file.

Command:
sudo cat /var/log/secure

Observation:
The failed sudo attempt was recorded in the secure log file.

Result:
Successfully created users and groups, assigned users to appropriate groups, verified memberships, switched between users, and observed Linux permission and sudo mechanisms.

Conclusion:
This lab provided practical experience in Linux user and group administration. It demonstrated how to manage user accounts, organize users into groups, verify permissions, and understand the importance of sudo privileges and system security logging.
