# Level 4

## Objective

Retrieve the password for **Level 5**. The password is stored in a **hidden file** inside the `inhere` directory.

## Challenge

By default, the `ls` command does not display hidden files. Hidden files and directories in Linux begin with a dot (`.`).

## Solution

First, move into the `inhere` directory:

```bash
cd inhere
```

List all files, including hidden ones:

```bash
ls -a
```
or 
```
ls -ahl
```
- a : Includes hidden files and folders in the output (beginning with a dot ., such as .bashrc or .git)
- h : Converts file sizes from raw bytes into easy-to-read formats like Kilobytes (K), Megabytes (M), or Gigabytes (G)
- l : : Displays permissions, ownership, exact file size, and the last modification date instead of just file names.

The output reveals the hidden file.

Read its contents using:

```bash
cat ..file_name
```

Replace `..file_name` with the actual filename displayed by `ls -a`.

This displays the password for the next level.

## Commands Used

```bash
cd inhere
ls -a
cat ...file_name
```
- Type `cd` and click `TAB` for auto fill the folder names or file names

## Concepts Learned

- Navigating directories with `cd`
- Viewing hidden files using `ls -a`
- Understanding that hidden files start with a dot (`.`)
- Reading file contents using `cat`

## Key Takeaway

The `ls` command hides files beginning with a dot (`.`) by default. Using the `-a` option displays all files, including hidden ones, allowing you to locate and access hidden data.
