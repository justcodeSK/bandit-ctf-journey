# Level 6

## Objective

Retrieve the password for **Level 7**. The password is stored **somewhere on the server** and has the following properties:

- Owned by user `bandit7`
- Owned by group `bandit6`
- Exactly **33 bytes** in size

## Challenge

Unlike previous levels, the file is not located in the current directory. Instead, it can be anywhere on the server, so searching manually would be impractical.

## Solution

Use the `find` command to search the entire filesystem while filtering by the required properties.

```bash
find / -type f -user bandit7 -group bandit6 -size 33c 2>/dev/null
```

### Command Breakdown

| Option | Description |
|--------|-------------|
| `/` | Start searching from the root directory |
| `-type f` | Search only regular files |
| `-user bandit7` | File must be owned by user `bandit7` |
| `-group bandit6` | File must belong to group `bandit6` |
| `-size 33c` | File size must be exactly 33 bytes |
| `2>/dev/null` | Suppress permission denied error messages |

The command returns the location of the password file.

## Reading the Password

Attempting to read the file using:

```bash
cat <file_path>
```

resulted in a **Permission denied** error.

Instead, I opened the file using:

```bash
nano <file_path>
```

which allowed me to view the password.

> **Note:** The official Bandit solution typically allows the file to be read with `cat`. If `cat` returns **Permission denied**, double-check that the path returned by `find` is correct and that you're logged into the expected Bandit level. In my session, I used `nano` to view the file contents.

## Commands Used

```bash
find / -type f -user bandit7 -group bandit6 -size 33c 2>/dev/null
nano <file_path>
```

## Concepts Learned

- Searching the entire filesystem with `find`
- Filtering by owner, group, and file size
- Redirecting error messages using `2>/dev/null`
- Understanding Linux file permissions
- Viewing files with `nano`

## Key Takeaway

The `find` command can combine multiple filters to quickly locate a specific file, even on a large filesystem. Redirecting errors to `/dev/null` keeps the output clean by hiding permission-related messages. If access to a file is denied, verify that you've found the correct file and that you're using the appropriate permissions.
