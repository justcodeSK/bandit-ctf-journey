# Level 5

## Objective

Retrieve the password for **Level 6**. The password is stored in the **only human-readable file** inside the `inhere` directory.

## Challenge

The `inhere` directory contains several files with similar names. Only one of them contains readable text, while the others contain binary data.

## Solution

Navigate to the `inhere` directory:

```bash
cd inhere
```

List the files:

```bash
ls -a
ls -hl
```

I manually checked the files using the `cat` command until I found the human-readable file.

```bash
cat ./-file07
```

This displayed the password for the next level.

## Commands Used

```bash
cd inhere
ls -a
ls -hl
cat ./-file07
```

## Better Approach

A more efficient solution is to use the `file` command to identify the human-readable file.

```bash
file ./*
```

The output indicates the file that contains **ASCII text**, which can then be read using:

```bash
cat ./-file07
```

## Concepts Learned

- Listing files with `ls`
- Viewing file sizes using `ls -hl`
- Reading file contents with `cat`
- Identifying file types using the `file` command
- Understanding the difference between text and binary files

## Key Takeaway

While it is possible to inspect files manually using `cat`, the `file` command is a faster and more reliable way to determine whether a file contains human-readable text or binary data.
