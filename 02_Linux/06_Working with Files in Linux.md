# Working with Files - Quick Revision

## Important Commands

### 1. hash

Displays cached command locations used by the shell.

```bash
hash
```

---

### 2. cksum

Verifies file integrity using a checksum.

```bash
cksum file.txt
```

---

### 3. find

Searches for files and directories.

```bash
find /home -name "*.txt"
find . -user yash
find . -size +10M
```

---

### 4. grep

Searches file contents for a text pattern.

```bash
grep Linux notes.txt
grep -i linux notes.txt
grep -n error logfile.log
```

---

### 5. diff

Compares two files line by line.

```bash
diff file1.txt file2.txt
```

Output is called a **diff**.

---

## File Links

### Hard Link

Creates another filename for the same file.

```bash
ln file.txt hardlink.txt
```

Characteristics:

- Same inode
- Survives original file deletion
- Cannot span file systems

---

### Symbolic Link (Soft Link)

Creates a shortcut to a file.

```bash
ln -s file.txt symlink.txt
```

Characteristics:

- Different inode
- Can span file systems
- Breaks if original file is deleted

---

## Hard Link vs Soft Link

| Feature | Hard Link | Soft Link |
|----------|-----------|-----------|
| Same Inode | Yes | No |
| Works Across File Systems | No | Yes |
| Survives Original File Deletion | Yes | No |
| Shortcut-like | No | Yes |

---

## Archiving and Compression

### tar

Bundles multiple files into one archive.

Create:

```bash
tar -cvf backup.tar folder/
```

Extract:

```bash
tar -xvf backup.tar
```

---

### gzip

Compresses a file.

```bash
gzip report.txt
```

Creates:

```text
report.txt.gz
```

Decompress:

```bash
gunzip report.txt.gz
```

---

### zip

Compresses files/directories.

```bash
zip backup.zip file.txt
zip -r backup.zip Documents
```

---

### unzip

Extracts ZIP files.

```bash
unzip backup.zip
```

---

## tar vs gzip vs zip

| Command | Purpose |
|----------|----------|
| tar | Archive files |
| gzip | Compress a file |
| zip | Archive + Compress |
| unzip | Extract ZIP archives |

---

## Key Takeaways

- `hash` → Shows cached commands.
- `cksum` → Verifies file integrity.
- `find` → Searches files.
- `grep` → Searches text inside files.
- `diff` → Compares files.
- `ln` → Creates file links.
- `tar` → Archives files.
- `gzip` → Compresses files.
- `zip` → Compresses files/directories.
- `unzip` → Extracts ZIP files.

---

## Memory Trick

### Search Tools

```text
F → Find files
G → Grep text
D → Diff files
```

### Compression Tools

```text
T → Tar
G → Gzip
Z → Zip
```

### Links

```text
Hard Link = Same File
Soft Link = Shortcut
```

---

## One-Line Exam Revision

Linux provides commands such as `find`, `grep`, and `diff` for searching and comparing files, `ln` for creating links, and `tar`, `gzip`, `zip`, and `unzip` for archiving and compression.