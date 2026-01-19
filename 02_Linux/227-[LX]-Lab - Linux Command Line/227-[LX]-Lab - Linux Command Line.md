Linux Command Line Lab Walkthrough

Aim:
To connect to an Amazon Linux EC2 instance using SSH and perform basic Linux command-line operations, including viewing system information and using command history features.

Requirements:
• AWS Academy Lab Environment
• AWS Management Console Access
• Amazon Linux EC2 Instance
• SSH Utility (PuTTY for Windows or Terminal for macOS/Linux)

Procedure:

Task 1: Connect to the Amazon Linux EC2 Instance

1. Started the AWS Lab by clicking the "Start Lab" button.
2. Waited until the lab status changed to "Ready".
3. Opened the AWS Management Console.
4. Retrieved the connection credentials from the Details section.
5. Downloaded the SSH key:

   * labsuser.ppk for Windows users, or
   * labsuser.pem for macOS/Linux users.
6. Noted the Public IP address of the EC2 instance.
7. Established an SSH connection to the EC2 instance.

For macOS/Linux:

Command:
ssh -i labsuser.pem ec2-user@<Public-IP>

For Windows:
Configured PuTTY with the downloaded PPK file and connected to the instance.

Observation:
Successfully logged in to the Amazon Linux EC2 instance as ec2-user.

Task 2: Execute Basic Linux Commands

1. Displayed the current user.

Command:
whoami

Output:
ec2-user

2. Displayed the short hostname.

Command:
hostname -s

Sample Output:
ip-10-x-x-x

3. Checked system uptime.

Command:
uptime -p

Sample Output:
up 2 hours, 30 minutes

4. Viewed information about logged-in users.

Command:
who -H -a

Observation:
Displayed user name, terminal line, login time, idle time, process ID, comments, and exit information.

5. Displayed the current date and time for New York.

Command:
TZ=America/New_York date

6. Displayed the current date and time for Los Angeles.

Command:
TZ=America/Los_Angeles date

Observation:
Verified that Linux can display time using different time zones.

7. Displayed the Julian calendar.

Command:
cal -j

Observation:
Observed the Julian day numbering system.

8. Displayed a Sunday-first calendar.

Command:
cal -s

9. Displayed a Monday-first calendar.

Command:
cal -m

10. Viewed user and group information.

Command:
id ec2-user

Observation:
Displayed the user ID, group ID, and group memberships.

Task 3: Use Command History and Search

1. Displayed the shell command history.

Command:
history

Observation:
Verified that previously executed commands were stored.

2. Performed reverse history search.

Procedure:
• Pressed CTRL + R.
• Typed TZ to search previously used commands.

Observation:
Retrieved previously executed timezone commands from history.

3. Displayed the current date.

Command:
date

4. Re-executed the previous command.

Command:
!!

Observation:
The last executed command ran again successfully.

Result:
Successfully connected to an Amazon Linux EC2 instance and executed various Linux commands to obtain system information. Also learned how to use Bash history, reverse search, and command reuse features to improve command-line efficiency.

Conclusion:
This lab provided hands-on experience with SSH connectivity, Linux system information commands, calendar utilities, user identification commands, and Bash history mechanisms. These skills are essential for effective Linux system administration and troubleshooting.
