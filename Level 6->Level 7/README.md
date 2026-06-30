# Level 6

## Objective

Retrieve the password for **Level 7**. The password is stored somewhere on the server with the following properties:

- Owned by user **bandit7**
- Owned by group **bandit6**
- Exactly **33 bytes** in size

## Challenge

Unlike previous levels, the password file is **not located in the current directory**. Instead, it is hidden somewhere on the server. Manually searching the filesystem would be impractical, so the `find` command is used to locate the file based on its properties.

## Solution

Search the entire filesystem for a file that matches all the given conditions:

```bash
find / -type f -user bandit7 -group bandit6 -size 33c 2>/dev/null
```

The command returns:

```text
/var/lib/dpkg/info/bandit7.password
```

Read the contents of the file:

```bash
cat /var/lib/dpkg/info/bandit7.password
```

This displays the password for the next level.

## Commands Used

```bash
find / -type f -user bandit7 -group bandit6 -size 33c 2>/dev/null
cat /var/lib/dpkg/info/bandit7.password
```

## Command Breakdown

### `find`

Searches for files and directories.

### `/`

Starts the search from the root directory, scanning the entire filesystem.

### `-type f`

Searches only for regular files.

### `-user bandit7`

Filters files owned by the user **bandit7**.

### `-group bandit6`

Filters files belonging to the group **bandit6**.

### `-size 33c`

Matches files that are exactly **33 bytes** in size.

> **Note:** The `c` stands for **bytes**.

### `2>/dev/null`

Redirects error messages (such as **Permission denied**) to `/dev/null`, keeping the output clean.

## Concepts Learned

- Searching the entire filesystem using `find`
- Filtering files by owner (`-user`)
- Filtering files by group (`-group`)
- Searching by exact file size (`-size`)
- Redirecting standard error using `2>/dev/null`

## Key Takeaway

The `find` command allows you to locate files efficiently by combining multiple search criteria such as owner, group, and file size. Redirecting error messages with `2>/dev/null` helps produce clean output when searching directories with restricted permissions.
