# GIT_guide
Excellent 👍 You uploaded the **Git Cheat Sheet (Education Edition)** — it lists essential Git commands, but it’s very short and lacks explanations or examples.

Let’s turn that into a **complete Git Guide with examples**, covering everything from setup to branching, merging, and collaboration — so you can actually understand and use each command.

---

# 🧭 Complete Git Guide with Examples

Git is a **version control system** used to track changes in code and collaborate with others.
Below is a structured, practical guide.

---

## 🧩 1. Git Setup & Configuration

### Install Git

👉 Download from [https://git-scm.com](https://git-scm.com)

### Configure your identity

```bash
git config --global user.name "Shubh Verma"
git config --global user.email "shubh@example.com"
```

> Sets your name and email for commits.

### Check your configuration

```bash
git config --list
```

---

## 🏁 2. Starting a Repository

### Initialize a new repository

```bash
git init
```

> Creates a new `.git` folder in your project directory.

### Clone an existing repo

```bash
git clone https://github.com/username/repo.git
```

> Copies a remote repository to your local system.

---

## 📦 3. Staging and Committing

### Check current status

```bash
git status
```

> Shows modified, staged, or untracked files.

### Stage files for commit

```bash
git add index.html
git add .
```

> Adds files to the staging area (ready to commit).

### Unstage files

```bash
git reset index.html
```

### Commit your changes

```bash
git commit -m "Added homepage UI"
```

> Saves a snapshot of your project history.

---

## 🌿 4. Branching and Merging

### Create a branch

```bash
git branch feature/login
```

### Switch to a branch

```bash
git checkout feature/login
```

### Combine a branch into main

```bash
git merge feature/login
```

> Merges changes from another branch into the current one.

### Delete a branch

```bash
git branch -d feature/login
```

---

## 🔄 5. Syncing with Remote Repositories

### Add a remote

```bash
git remote add origin https://github.com/username/repo.git
```

### Push your commits

```bash
git push origin main
```

### Pull latest changes

```bash
git pull
```

### Fetch updates without merging

```bash
git fetch origin
```

---

## 🗑️ 6. Undoing Changes

### Discard changes in a file

```bash
git checkout -- app.js
```

### Reset to a previous commit

```bash
git reset --hard <commit-id>
```

### View commit history

```bash
git log
```

---

## 📂 7. File and Path Changes

### Rename or move a file

```bash
git mv oldname.txt newname.txt
```

### Remove a file

```bash
git rm unwanted.txt
```

---

## 📦 8. Stashing (Temporary Saves)

### Save your current changes

```bash
git stash
```

### Show stashed changes

```bash
git stash list
```

### Reapply last stash

```bash
git stash pop
```

---

## 🕵️ 9. Inspect & Compare

### Compare unstaged changes

```bash
git diff
```

### Compare staged changes

```bash
git diff --staged
```

### Compare two branches

```bash
git diff main...feature/login
```

---

## 🚫 10. Ignoring Files

Create a `.gitignore` file:

```
node_modules/
.env
logs/
*.tmp
```

> Prevents Git from tracking those files.

---

## 🧰 11. Rewriting History

### Rebase current branch

```bash
git rebase main
```

### Undo all local changes

```bash
git reset --hard HEAD
```

---

## 🔍 12. Practical Workflow Example

```bash
# 1. Clone repo
git clone https://github.com/user/project.git
cd project

# 2. Create feature branch
git checkout -b feature/api

# 3. Make changes & commit
git add .
git commit -m "Added API integration"

# 4. Merge to main
git checkout main
git merge feature/api

# 5. Push to GitHub
git push origin main
```

---

## 🧠 13. Useful Tips

| Task                       | Command                                |
| -------------------------- | -------------------------------------- |
| View recent commits        | `git log --oneline --graph --decorate` |
| Rename last commit message | `git commit --amend -m "new message"`  |
| Check remote URLs          | `git remote -v`                        |
| Delete remote branch       | `git push origin --delete branch-name` |

---

Would you like me to generate this guide as a **PDF file** (formatted neatly with sections, color headers, and syntax highlighting) so you can keep it offline?
