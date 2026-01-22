# Editing Files Lab Walkthrough

## Objective

In this lab, I used `vimtutor` to learn Vim basics, created and edited files with Vim, and then created and edited files with Nano.

---

# Task 1: Connect to the EC2 Instance

If I was already connected from a previous lab, I could skip this step.

I moved to the Downloads folder, updated the PEM file permissions, and connected to the EC2 instance with SSH.

```bash
cd ~/Downloads
chmod 400 labsuser.pem
ssh -i labsuser.pem ec2-user@<Public-IP>
```

---

# Task 2: Run Vim Tutor

I started Vim Tutor with:

```bash
vimtutor
```

If `vimtutor` was not available, I installed Vim first:

```bash
sudo yum install vim -y
```

Then I ran `vimtutor` again and completed the first three lessons, which covered moving the cursor, deleting text, inserting text, saving files, and quitting Vim.

When I was finished, I exited Vim Tutor with:

```vim
:q!
```

---

# Task 3: Edit a File Using Vim

I created a file in Vim:

```bash
vim helloworld
```

After opening the file, I entered insert mode by pressing `i`, then typed the following text:

```text
Hello World!
This is my first file in Linux and I am editing it in Vim!
```

I exited insert mode with `ESC` and saved the file with:

```vim
:wq
```

Later, I opened the file again, entered insert mode, and added one more line:

```text
I learned how to create a file, edit and save them too!
```

This time, I exited without saving using:

```vim
:q!
```

When I reopened the file, I confirmed that the last line was not saved.

I also practiced a few useful Vim commands:

* `dd` to delete the current line
* `u` to undo the last action
* `:w` to save without quitting

---

# Task 4: Edit a File Using Nano

I created a Nano file with:

```bash
nano cloudworld
```

Then I typed:

```text
We are using nano this time! We can simply start typing! No insert mode needed.
```

To save the file, I pressed `CTRL + O`, confirmed the filename, and pressed `Enter`.

I exited Nano with:

```text
CTRL + X
```

After reopening the file, I confirmed that the text was saved correctly.

---

# Important Commands Summary

| Action                | Command           |
| --------------------- | ----------------- |
| Start Vim Tutor       | `vimtutor`        |
| Open/Create Vim File  | `vim helloworld`  |
| Insert Mode           | `i`               |
| Exit Insert Mode      | `ESC`             |
| Save and Quit         | `:wq`             |
| Quit Without Saving   | `:q!`             |
| Delete Line           | `dd`              |
| Undo                  | `u`               |
| Save Without Quitting | `:w`              |
| Open Nano File        | `nano cloudworld` |
| Save in Nano          | `CTRL + O`        |
| Exit Nano             | `CTRL + X`        |

---

## Result

I successfully used Vim Tutor, created and edited files with Vim, and created and edited files with Nano.
