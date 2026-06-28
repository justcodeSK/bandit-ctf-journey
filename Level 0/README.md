# Level 0

## Objective

Connect to the Bandit server using SSH and obtain access to the first level.

## Connection Details

```bash
ssh bandit0@bandit.labs.overthewire.org -p 2220
```

**Username:**

```text
bandit0
```

**Password:**

```text
bandit0
```

After entering the password, you will successfully log in to the Bandit server.

## Commands Used

```bash
ssh bandit0@bandit.labs.overthewire.org -p 2220
```

## Concepts Learned

- What SSH is
- Connecting to a remote Linux server
- Logging in using a username and password
- Specifying a custom SSH port using `-p`

## Key Takeaway

SSH (Secure Shell) is a secure protocol used to remotely access Linux systems. Throughout the Bandit wargame, SSH is used to connect to each new level using the password obtained from the previous challenge.
