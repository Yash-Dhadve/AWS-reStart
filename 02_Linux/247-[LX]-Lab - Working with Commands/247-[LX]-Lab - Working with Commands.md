# Working with Commands Lab – Step-by-Step Walkthrough

## Aim

To understand the usage of Linux text-processing commands such as tee, sort, cut, sed, and the pipe operator for manipulating and processing file contents.

---

## Step 1: Connect to the EC2 Instance

1. Started the AWS Academy Lab environment.
2. Opened the AWS Management Console.
3. Downloaded the PEM/PPK key file and noted the Public IP address.
4. Connected to the Amazon Linux EC2 instance using SSH.
5. Verified successful login as the ec2-user.

Command Used:

```bash
ssh -i labsuser.pem ec2-user@<Public-IP>
```

---

## Step 2: Use the tee Command

1. Verified the current working directory.

Command Used:

```bash
pwd
```

2. Used the hostname command and redirected its output to both the screen and a file using the tee command.

Command Used:

```bash
hostname | tee file1.txt
```

3. Observed that the hostname was displayed on the terminal and simultaneously written to the file named file1.txt.

4. Verified that the file was created successfully.

Command Used:

```bash
ls
```

Expected Output:

```text
companyA  file1.txt
```

---

## Step 3: Use the sort Command and Pipe Operator

1. Verified the current working directory.

Command Used:

```bash
pwd
```

2. Created a file named test.csv.

Command Used:

```bash
cat > test.csv
```

3. Entered the following data:

```text
Factory, 1, Paris
Store, 2, Dubai
Factory, 3, Brasilia
Store, 4, Algiers
Factory, 5, Tokyo
```

4. Pressed CTRL + D to save and close the file.

5. Verified file creation.

Command Used:

```bash
ls
```

6. Sorted the contents of the file alphabetically.

Command Used:

```bash
sort test.csv
```

Expected Output:

```text
Factory, 1, Paris
Factory, 3, Brasilia
Factory, 5, Tokyo
Store, 2, Dubai
Store, 4, Algiers
```

7. Used the pipe operator and grep command to search for the Paris entry.

Command Used:

```bash
grep Paris test.csv
```

Expected Output:

```text
Factory, 1, Paris
```

8. Verified that the record containing Paris was successfully located.

---

## Step 4: Use the cut Command

1. Created a file named cities.csv.

Command Used:

```bash
cat > cities.csv
```

2. Entered the following data:

```text
Dallas, Texas
Seattle, Washington
Los Angeles, California
Atlanta, Georgia
New York, New York
```

3. Pressed CTRL + D to save the file.

4. Used the cut command to extract only the city names.

Command Used:

```bash
cut -d ',' -f 1 cities.csv
```

Expected Output:

```text
Dallas
Seattle
Los Angeles
Atlanta
New York
```

5. Verified that everything after the comma was removed from the output.

---

## Step 5: Use the sed Command

1. Used the sed command to replace the first comma with a period in cities.csv.

Command Used:

```bash
sed 's/,/./' cities.csv
```

Expected Output:

```text
Dallas. Texas
Seattle. Washington
Los Angeles. California
Atlanta. Georgia
New York. New York
```

2. Used the sed command on test.csv.

Command Used:

```bash
sed 's/,/./' test.csv
```

Expected Output:

```text
Factory. 1, Paris
Store. 2, Dubai
Factory. 3, Brasilia
Store. 4, Algiers
Factory. 5, Tokyo
```

3. Verified that only the first comma in each line was replaced.

---

## Verification

### Verify file1.txt

```bash
cat file1.txt
```

### Verify test.csv

```bash
cat test.csv
```

### Verify cities.csv

```bash
cat cities.csv
```

### Verify Sort Output

```bash
sort test.csv
```

### Verify Cut Output

```bash
cut -d ',' -f 1 cities.csv
```

### Verify Sed Output

```bash
sed 's/,/./' cities.csv
sed 's/,/./' test.csv
```

---

## Result

Successfully used the tee command to write output to both a file and the terminal, sorted records using the sort command, extracted fields using the cut command, searched records using the pipe operator and grep command, and modified text using the sed command.

---

## Conclusion

This lab provided practical experience with Linux text-processing utilities. It demonstrated how commands such as tee, sort, cut, sed, and the pipe operator can be used together to process, filter, modify, and analyze file contents efficiently. These commands are essential tools for Linux system administration and shell scripting.
