# Level 7

## Objective

Retrieve the password for **Level 8**. The password is stored in the file `data.txt` next to the word **`millionth`**.

## Challenge

The file `data.txt` contains a large amount of text, making it inefficient to search manually. The goal is to locate the line containing the word **`millionth`**.

## Solution

First, list the files in the current directory:

```bash
ls
```

Locate the line containing the word `millionth` using the `grep` command:

```bash
grep "millionth" data.txt
```

The output displays the word `millionth` followed by the password for the next level.

## Commands Used

```bash
ls
grep "millionth" data.txt
```

## Command Breakdown

```bash
grep "millionth" data.txt
```

| Part | Description |
|------|-------------|
| `grep` | Searches for lines matching a given pattern |
| `"millionth"` | The word to search for |
| `data.txt` | The file to search in |

## Concepts Learned

- Searching text files using `grep`
- Finding specific words or patterns within a file
- Efficiently locating information in large text files

## Key Takeaway

The `grep` command is one of the most useful Linux utilities for searching text. Instead of manually reading large files, `grep` quickly filters and displays only the lines that match a specified pattern, making it an essential tool for system administration, scripting, and cybersecurity.
