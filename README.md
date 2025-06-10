# Git Stash Practical Guide

## 🔧 What is `git stash`?

`git stash` temporarily shelves (or stashes) changes you've made to your working directory so you can work on something else, then come back and re-apply them later.

---

## 📁 Practical Scenario Setup

1. **Initialize a Git repo and create a file:**

```bash
mkdir stash-demo && cd stash-demo
git init
echo "Line 1" > file.txt
git add file.txt
git commit -m "Initial commit"
```

2. **Make some changes:**

```bash
echo "Line 2" >> file.txt
```

---

## 🚀 Practical Git Stash Commands

### 1. `git stash` – Save your changes

```bash
git stash
```

🔹 This saves *tracked file* changes and clears the working directory.

---

### 2. `git stash list` – See saved stashes

```bash
git stash list
```

🔹 Output example:
```
stash@{0}: WIP on main: 1234567 Initial commit
```

---

### 3. `git stash show` – View summary of changes

```bash
git stash show
```

🔹 To see full diff:
```bash
git stash show -p
```

---

### 4. `git stash apply` – Re-apply changes (keep stash)

```bash
git stash apply
```

🔹 This reapplies the last stash but **keeps it in the stash list**.

---

### 5. `git stash pop` – Re-apply changes (and remove stash)

```bash
git stash pop
```

🔹 Reapplies and **removes** the stash from the list.

---

### 6. `git stash drop` – Delete a specific stash

```bash
git stash drop stash@{0}
```

---

### 7. `git stash clear` – Remove **all** stashes

```bash
git stash clear
```

---

### 8. `git stash -u` – Include untracked files

```bash
git stash -u
```

🔹 Saves changes including untracked files (`-u` = untracked).

---

### 9. `git stash push -m "msg"` – Save with a message

```bash
git stash push -m "Added Line 2"
```

🔹 This helps identify stashes by purpose.

---

### 10. `git stash branch <branchname>` – Create branch from stash

```bash
git stash branch feature1 stash@{0}
```

🔹 Creates a new branch, checks it out, and applies the stash.

---

## 📌 Summary Table

| Command                     | Description                            |
|----------------------------|----------------------------------------|
| `git stash`                | Save changes                           |
| `git stash list`           | View all stashes                       |
| `git stash show [-p]`      | Show stash diff                        |
| `git stash apply`          | Reapply changes                        |
| `git stash pop`            | Reapply & delete stash                 |
| `git stash drop {n}`       | Delete specific stash                  |
| `git stash clear`          | Delete all stashes                     |
| `git stash -u`             | Stash + untracked files                |
| `git stash push -m "msg"`  | Stash with message                     |
| `git stash branch <name>`  | New branch from stash                  |
