# Working with the File System Lab Walkthrough

## Objective

In this lab, I created folders and files, copied and moved items, deleted files and directories, and reorganized a folder structure.

---

# Task 1: Connect to EC2

If I was already connected from a previous lab, I skipped this step.

```bash
cd ~/Downloads
chmod 400 labsuser.pem
ssh -i labsuser.pem ec2-user@<Public-IP>
```

---

# Task 2: Create the Initial Folder Structure

I first checked my current directory:

```bash
pwd
```

The expected location was:

```text
/home/ec2-user
```

If I was not in the home directory, I moved there with:

```bash
cd /home/ec2-user
```

I then created the `CompanyA` folder and moved into it:

```bash
mkdir CompanyA
cd CompanyA
```

Next, I created the department folders:

```bash
mkdir Finance HR Management
```

Inside `HR`, I created the files:

```bash
cd HR
touch Assessments.csv TrialPeriod.csv
```

Inside `Finance`, I created:

```bash
cd ../Finance
touch Salary.csv ProfitAndLossStatements.csv
```

For `Management`, I created the files from the parent directory:

```bash
cd ..
touch Management/Managers.csv Management/Schedule.csv
```

I checked the structure with:

```bash
ls -laR
```

---

# Task 3: Reorganize Folder Structure

I confirmed that I was in:

```bash
/home/ec2-user/CompanyA
```

To copy the Finance folder into HR, I ran:

```bash
cp -r Finance HR
```

I verified the copied files inside `HR/Finance`.

Then I removed the original Finance files and deleted the empty folder:

```bash
rm Finance/ProfitAndLossStatements.csv Finance/Salary.csv
rmdir Finance
```

After that, I moved `Management` into `HR`:

```bash
mv Management HR
```

I created an `Employees` folder inside `HR`:

```bash
cd HR
mkdir Employees
```

Finally, I moved the HR files into `Employees`:

```bash
mv Assessments.csv TrialPeriod.csv Employees
```

I verified the final folder structure before finishing.

---

# Commands Learned

| Command | Purpose                      |
| ------- | ---------------------------- |
| `pwd`   | Show current directory       |
| `cd`    | Change directory             |
| `mkdir` | Create directory             |
| `touch` | Create empty files           |
| `ls`    | List contents                |
| `ls -laR` | Recursive listing          |
| `cp -r` | Copy directories recursively |
| `rm`    | Remove files                 |
| `rmdir` | Remove empty directories     |
| `mv`    | Move files/directories       |

---

## Result

I successfully created the required directory structure, generated files, copied and moved directories, deleted files and folders, and reorganized the `CompanyA` folder structure as required.
