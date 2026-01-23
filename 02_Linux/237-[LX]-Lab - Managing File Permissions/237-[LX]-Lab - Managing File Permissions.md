# Managing File Permissions Lab – Step-by-Step Walkthrough

## Aim

To understand and implement Linux file ownership and permission management by modifying ownership, changing permission modes, and assigning permissions to different users and groups.

---

## Step 1: Connect to the EC2 Instance

1. Started the AWS Academy Lab environment.
2. Opened the AWS Management Console.
3. Downloaded the PEM/PPK key file and noted the Public IP address.
4. Established an SSH connection with the Amazon Linux EC2 instance.
5. Verified successful login as the ec2-user.

Command Used:

```bash
ssh -i labsuser.pem ec2-user@<Public-IP>
```

---

## Step 2: Change File and Folder Ownership

1. Verified the current working directory.

Command Used:

```bash
pwd
```

2. Navigated to the companyA directory if required.

Command Used:

```bash
cd companyA
```

3. Changed the ownership of the entire companyA directory structure to the CEO and Personnel group.

Command Used:

```bash
sudo chown -R mjackson:Personnel /home/ec2-user/companyA
```

4. Changed ownership of the HR directory to the HR Manager and HR group.

Command Used:

```bash
sudo chown -R ljuan:HR HR
```

5. Changed ownership of the Finance directory to the Finance Manager and Finance group.

Command Used:

```bash
sudo chown -R mmajor:Finance HR/Finance
```

6. Verified ownership changes recursively.

Command Used:

```bash
ls -laR
```

7. Confirmed that ownership changes had been applied successfully throughout the directory structure.

---

## Step 3: Change Permission Modes

### Creating and Modifying Permissions Using Symbolic Mode

1. Created a file named symbolic_mode_file using Vim.

Command Used:

```bash
sudo vi symbolic_mode_file
```

2. Saved and exited the file using:

```vim
:wq
```

3. Granted write permission to the group owner using symbolic mode.

Command Used:

```bash
sudo chmod g+w symbolic_mode_file
```

4. Verified that the group now had write access to the file.

---

### Creating and Modifying Permissions Using Absolute Mode

1. Created another file named absolute_mode_file.

Command Used:

```bash
sudo vi absolute_mode_file
```

2. Saved and exited the file.

```vim
:wq
```

3. Changed file permissions using absolute mode.

Command Used:

```bash
sudo chmod 764 absolute_mode_file
```

4. Under the permission value 764:

* Owner: Read, Write, Execute
* Group: Read, Write
* Others: Read

5. Verified permissions of both files.

Command Used:

```bash
ls -l
```

6. Confirmed that the permissions were correctly assigned.

---

## Step 4: Assign Permissions to Shipping and Sales

1. Verified that the current directory was companyA.

Command Used:

```bash
pwd
```

2. Changed ownership of the Shipping directory to the Shipping Manager and Shipping group.

Command Used:

```bash
sudo chown -R eowusu:Shipping Shipping
```

3. Changed ownership of the Sales directory to the Sales Manager and Sales group.

Command Used:

```bash
sudo chown -R nwolf:Sales Sales
```

4. Verified ownership changes in the Shipping directory.

Command Used:

```bash
ls -laR Shipping
```

5. Verified ownership changes in the Sales directory.

Command Used:

```bash
ls -laR Sales
```

6. Confirmed that both directories and their contents reflected the correct ownership information.

---

## Verification

The following checks were performed:

### Verify Company Ownership

```bash
ls -laR
```

### Verify File Permissions

```bash
ls -l
```

### Verify Shipping Ownership

```bash
ls -laR Shipping
```

### Verify Sales Ownership

```bash
ls -laR Sales
```

All ownership and permission settings were verified successfully.

---

## Result

Successfully changed file and directory ownership, modified permissions using both symbolic and absolute modes, and assigned appropriate ownership to the Shipping and Sales directories.

---

## Conclusion

This lab provided practical experience in Linux permission management. It demonstrated how to manage ownership using the chown command, modify permissions using chmod in both symbolic and numeric formats, and verify access rights using directory listing commands. These concepts are fundamental for securing Linux systems and controlling user access to files and directories.
