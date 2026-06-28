# Level 3

## Objective

Retrieve the password for **Level 4** from a file named:

```text
--spaces in this filename--
```

located in the home directory.

## Challenge

The filename contains spaces, so entering it without quotes causes the shell to treat each word as a separate argument.

## Solution

List the files in the current directory:

```bash
ls
```

Read the file by enclosing the filename in double quotes:

```bash
cat ./"--spaces in this filename--"
```

This displays the password for the next level.

## Commands Used

```bash
ls
cat ./"--spaces in this filename--"
```

## Alternative Solution

Instead of using quotes, you can escape each space with a backslash (`\`):

```bash
cat ./--spaces\ in\ this\ filename--
```

## Concepts Learned

- Handling filenames containing spaces
- Using quotes (`""`) to treat a filename as a single argument
- Using the `./` prefix to specify a file in the current directory
- Escaping spaces with the backslash (`\`) character

## Key Takeaway

When a filename contains spaces, the shell splits it into separate arguments. Enclosing the filename in quotes or escaping each space ensures it is interpreted as a single filename.
