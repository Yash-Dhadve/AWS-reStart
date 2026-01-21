# Managing Users and Groups Lab Walkthrough

## Aim

In this lab, I created users and groups in Linux, assigned users to the correct groups, verified group memberships, and reviewed sudo access and user switching.

## Requirements

* AWS Academy Lab Environment
* Amazon Linux EC2 Instance
* SSH Access such as PuTTY or Terminal

## Procedure

### Task 1: Connect to the EC2 Instance

I started the lab, waited for the status to become **Ready**, opened the AWS Management Console, downloaded the SSH key file, noted the public IP address, and connected to the EC2 instance using SSH.

For macOS/Linux:

```bash
ssh -i labsuser.pem ec2-user@<Public-IP>
```

After connecting, I confirmed that I was logged in as `ec2-user`.

### Task 2: Create Users

I checked my current location with:

```bash
pwd
```

This showed:

```text
/home/ec2-user
```

I then created the required user accounts with `useradd` and set passwords for them with `passwd`.

Example:

```bash
sudo useradd arosalez
sudo passwd arosalez
```

I repeated that process for the following users:

* arosalez
* eowusu
* jdoe
* ljuan
* mmajor
* mjackson
* nwolf
* psantos
* smartinez
* ssarkar

To verify the accounts, I listed the usernames from `/etc/passwd` and confirmed that the new users were present.

### Task 3: Create Groups

I created the required groups with `groupadd`:

* Sales
* HR
* Finance
* Shipping
* Managers
* CEO

Example:

```bash
sudo groupadd Sales
```

I verified the group list in `/etc/group`, then added the users to their assigned groups.

Group memberships:

* Sales: arosalez, nwolf
* HR: ljuan, smartinez
* Finance: mmajor, ssarkar
* Shipping: eowusu, jdoe, psantos
* Managers: arosalez, ljuan, mmajor
* CEO: mjackson

I also added `ec2-user` to all of the groups and then checked `/etc/group` again to confirm everything was set correctly.

### Task 4: Test User Login and Sudo Access

I switched to another user with:

```bash
su arosalez
```

After entering the password, I checked the current directory:

```bash
pwd
```

The location remained in `/home/ec2-user`, which showed that the shell context did not move to a different home directory automatically.

I tried creating a file:

```bash
touch myFile.txt
```

That failed with a permission error because `arosalez` did not have write access to the `ec2-user` home directory.

I also tried using `sudo`:

```bash
sudo touch myFile.txt
```

This returned the message that `arosalez` was not in the sudoers file, which confirmed that the user did not have administrative privileges.

After that, I returned to `ec2-user` with:

```bash
exit
```

Finally, I checked the secure log file:

```bash
sudo cat /var/log/secure
```

That showed the failed sudo attempt in the system log.

## Result

I successfully created users and groups, assigned users to the correct groups, verified memberships, switched between users, and observed how Linux handles permissions and sudo access.

## Conclusion

This lab gave me practical experience with Linux user and group administration. I learned how to manage user accounts, organize users into groups, verify permissions, and understand the role of sudo privileges and security logging.
