# Working with Files Lab – Step-by-Step Walkthrough

## Aim

To create a compressed backup of a directory structure using the tar utility, maintain a backup log file, and transfer the backup archive to another directory.

---

## Step 1: Connect to the EC2 Instance

1. Started the AWS Academy Lab environment.
2. Opened the AWS Management Console.
3. Downloaded the PEM key file and noted the Public IP address.
4. Connected to the Amazon Linux EC2 instance using SSH.

Command Used:

```bash
ssh -i labsuser.pem ec2-user@<Public-IP>
```

5. Verified successful login to the EC2 instance.

---

## Step 2: Verify the Existing Directory Structure

1. Checked the current working directory.

Command Used:

```bash
pwd
```

Output:

```text
/home/ec2-user
```

2. Displayed the contents of the CompanyA directory structure.

Command Used:

```bash
ls -R CompanyA
```

3. Verified the presence of all folders and files inside the CompanyA directory.

---

## Step 3: Create a Backup Archive

1. Created a compressed backup archive of the entire CompanyA directory.

Command Used:

```bash
tar -csvpzf backup.CompanyA.tar.gz CompanyA
```

2. Observed the files and folders being added to the archive.

3. Verified that the backup archive was created successfully.

Command Used:

```bash
ls
```

Output:

```text
backup.CompanyA.tar.gz
CompanyA
```

4. Confirmed that the backup archive contained the complete CompanyA directory structure.

---

## Step 4: Create a Backup Log

1. Navigated to the CompanyA directory.

Command Used:

```bash
cd /home/ec2-user/CompanyA
```

2. Created a backup log file.

Command Used:

```bash
touch SharedFolders/backups.csv
```

3. Added the backup date, time, and archive name to the log file.

Command Used:

```bash
echo "25 Aug 25 2021, 16:59, backup.CompanyA.tar.gz" | sudo tee SharedFolders/backups.csv
```

4. Verified the contents of the backup log file.

Command Used:

```bash
cat SharedFolders/backups.csv
```

Output:

```text
25 Aug 25 2021, 16:59, backup.CompanyA.tar.gz
```

5. Confirmed that the backup information was stored correctly.

---

## Step 5: Move the Backup Archive

1. Verified the current working directory.

Command Used:

```bash
pwd
```

Output:

```text
/home/ec2-user/CompanyA
```

2. Moved the backup archive to the IA directory.

Command Used:

```bash
mv ../backup.CompanyA.tar.gz IA/
```

3. Verified the transfer of the backup archive.

Command Used:

```bash
ls . IA
```

Output:

```text
.:
Employees Finance HR IA Management SharedFolders

IA:
backup.CompanyA.tar.gz
```

4. Confirmed that the archive file had been successfully transferred to the IA directory.

---

## Verification

The following checks were performed:

### Verify Backup Archive

```bash
ls IA
```

Expected Output:

```text
backup.CompanyA.tar.gz
```

### Verify Backup Log

```bash
cat SharedFolders/backups.csv
```

Expected Output:

```text
25 Aug 25 2021, 16:59, backup.CompanyA.tar.gz
```

---

## Result

Successfully created a compressed backup archive of the CompanyA directory structure using the tar utility, maintained a backup log file containing the backup details, and transferred the backup archive to the IA directory.

---

## Conclusion

This lab demonstrated the process of creating compressed backups using the tar utility, maintaining backup records for administrative purposes, and transferring backup archives between directories. These operations are essential tasks for Linux system administrators to ensure proper backup management, data protection, and recovery readiness.
