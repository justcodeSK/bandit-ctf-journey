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

The output reveals the hidden file.

Read its contents using:

```bash
cat .<hidden_filename>
```

Replace `<hidden_filename>` with the actual filename displayed by `ls -a`.

This displays the password for the next level.

## Commands Used

```bash
cd inhere
ls -a
cat .<hidden_filename>
```

## Concepts Learned

- Navigating directories with `cd`
- Viewing hidden files using `ls -a`
- Understanding that hidden files start with a dot (`.`)
- Reading file contents using `cat`

## Key Takeaway

The `ls` command hides files beginning with a dot (`.`) by default. Using the `-a` option displays all files, including hidden ones, allowing you to locate and access hidden data.
