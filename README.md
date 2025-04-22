# dsclean

*A simple utility to clean up `.DS_Store` files from your projects before you share.*

---

## Why I Made This

If you work on MacOS and collaborate with others (especially Windows or Linux users), you know the pain of `.DS_Store` files showing up everywhere in your repository.

I searched high and low for a simple, direct command-line tool that:  
- Cleans only what I want, recursively or not  
- Plays nicely in scripts and git workflows  
- Doesn't flood my terminal with output (unless I want it)  
- Just works™

I couldn't find a tool that hit all the marks, so I made this in like 15 minutes.

---

## Installation

1. **Download the script** to your Mac:
   ```sh
   sudo curl -o /usr/local/bin/dsclean https://raw.githubusercontent.com/octiwhale/dsclean/main/dsclean
   sudo chmod +x /usr/local/bin/dsclean
   ```

2. Now the `dsclean` command is ready to go anywhere in your terminal.

---

## Usage

**Clean current directory and subdirectories:**
```sh
dsclean
```

**Clean a specific folder and its children:**
```sh
dsclean /path/to/dir
```

**Just the current folder (non-recursive):**
```sh
dsclean --parent
```

**Just a specific folder (non-recursive):**
```sh
dsclean -p /path/to/dir
```

**Show each file as it’s deleted:**
```sh
dsclean -v
```

---

## Example for Git

Add to your `.git/hooks/pre-commit` to prevent `.DS_Store` files from sneaking into your commits:
```sh
#!/bin/bash
dsclean
```
