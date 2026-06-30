# Level 5

## Objective

Retrieve the password for **Level 6**. The password is stored in a file somewhere under the `inhere` directory with the following properties:

- Human-readable
- Exactly **1033 bytes** in size
- Not executable

## Solution

Instead of manually searching through every directory, use the `find` command to locate the file based on its properties.

```bash
find inhere -type f -size 1033c ! -executable
```

The command returns the path to the matching file.

```text
inhere/maybehere07/.file2
```

Read the file to obtain the password:

```bash
cat inhere/maybehere07/.file2
```

## Commands Used

```bash
find inhere -type f -size 1033c ! -executable
cat inhere/maybehere07/.file2
```

## Understanding the `find` Command

```bash
find inhere -type f -size 1033c ! -executable
```

| Option | Description |
|--------|-------------|
| `find` | Searches for files and directories. |
| `inhere` | Directory where the search begins. |
| `-type f` | Search only for regular files. |
| `-size 1033c` | Match files that are exactly **1033 bytes** (`c` = bytes). |
| `! -executable` | Exclude executable files. |

## Concepts Learned

- Using `find` to search for files.
- Filtering by file type with `-type`.
- Filtering by exact file size using `-size`.
- Excluding executable files with `! -executable`.
- Reading file contents with `cat`.

## Key Takeaway

The `find` command allows you to efficiently locate files based on multiple conditions, such as file type, size, and permissions. Combining these filters makes it much easier to find a specific file without manually browsing through directories.
