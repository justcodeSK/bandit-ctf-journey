# Level 2

## Objective

Retrieve the password for **Level 3** from a file whose name begins with a hyphen (`-`).

## Challenge

Listing the files reveals a file named `-`.

```bash
ls
```

Trying to read it directly:

```bash
cat -
```

does not work because the hyphen (`-`) is interpreted as an option (or standard input) rather than a filename.

## Solution

The file is named `-`, which Linux may interpret as an option rather than a filename.

One way to read it is by specifying its path relative to the current directory:

```bash
cat ./-
```

Since the file is also located in the home directory, it can alternatively be accessed using:

```bash
cat ~/-
```

Both commands treat `-` as part of the file path instead of as a command option.

This displays the password for the next level.

## Commands Used

```bash
ls
cat ./-
```

## Understanding Filenames Starting with `-`

In Linux, filenames beginning with a hyphen (`-`) can be mistaken for command-line options. There are two common ways to work with such files.

### 1. Use the current directory prefix (`./`)

This tells the command that the argument is a file path.

```bash
cat ./-filename
touch ./-filename
```

### 2. Use the `--` option terminator

The double dash (`--`) tells the command that everything following it should be treated as an argument, not an option.

```bash
rm -- -filename
touch -- -filename
cat -- -filename
```

## Concepts Learned

- Handling filenames that begin with `-`
- Using `./` to reference files in the current directory
- Using `--` to stop option parsing
- Understanding how Linux commands interpret command-line arguments

## Key Takeaway

Linux commands treat filenames beginning with `-` as command options. To access these files safely, either prepend the filename with `./` or use the `--` option terminator.
