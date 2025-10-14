Perfect 👍 — you want a **Git guide where each command shows first the syntax, then an example** (clear and practical).

Here’s the **clean, structured version** of the full Git guide in that format 👇

---

# 🧭 Complete Git Guide (Syntax + Example)

---

## ⚙️ 1. Git Setup

### 🧩 Syntax:

```bash
git config --global user.name "[your name]"
git config --global user.email "[your email]"
```

### 💡 Example:

```bash
git config --global user.name "Shubh Verma"
git config --global user.email "shubh@example.com"
```

---

### 🧩 Syntax:

```bash
git config --list
```

### 💡 Example:

```bash
git config --list
# user.name=Shubh Verma
# user.email=shubh@example.com
```

---

## 🏁 2. Initialize or Clone Repository

### 🧩 Syntax:

```bash
git init
```

### 💡 Example:

```bash
git init
# Initialized empty Git repository in /myproject/.git/
```

---

### 🧩 Syntax:

```bash
git clone [url]
```

### 💡 Example:

```bash
git clone https://github.com/shubhverma/weather-app.git
# Clones the repository into a folder named weather-app
```

---

## 📦 3. Staging and Committing

### 🧩 Syntax:

```bash
git status
```

### 💡 Example:

```bash
git status
# Shows modified, staged, and untracked files
```

---

### 🧩 Syntax:

```bash
git add [file]
```

### 💡 Example:

```bash
git add index.html
```

---

### 🧩 Syntax:

```bash
git add .
```

### 💡 Example:

```bash
git add .
# Adds all files in the directory to staging
```

---

### 🧩 Syntax:

```bash
git commit -m "[message]"
```

### 💡 Example:

```bash
git commit -m "Added login feature"
```

---

## 🌿 4. Branching and Merging

### 🧩 Syntax:

```bash
git branch
```

### 💡 Example:

```bash
git branch
# * main
# feature/login
```

---

### 🧩 Syntax:

```bash
git branch [branch-name]
```

### 💡 Example:

```bash
git branch feature/payment
```

---

### 🧩 Syntax:

```bash
git checkout [branch-name]
```

### 💡 Example:

```bash
git checkout feature/payment
```

---

### 🧩 Syntax:

```bash
git merge [branch-name]
```

### 💡 Example:

```bash
git merge feature/payment
# Merges “feature/payment” into the current branch
```

---

## 🔄 5. Remote Repositories

### 🧩 Syntax:

```bash
git remote add [alias] [url]
```

### 💡 Example:

```bash
git remote add origin https://github.com/shubhverma/weather-app.git
```

---

### 🧩 Syntax:

```bash
git push [alias] [branch]
```

### 💡 Example:

```bash
git push origin main
```

---

### 🧩 Syntax:

```bash
git pull
```

### 💡 Example:

```bash
git pull
# Fetches and merges latest changes from remote
```

---

### 🧩 Syntax:

```bash
git fetch [alias]
```

### 💡 Example:

```bash
git fetch origin
```

---

## 🗂️ 6. File Changes

### 🧩 Syntax:

```bash
git mv [old-name] [new-name]
```

### 💡 Example:

```bash
git mv oldfile.txt newfile.txt
```

---

### 🧩 Syntax:

```bash
git rm [file]
```

### 💡 Example:

```bash
git rm notes.txt
```

---

## 🧹 7. Undoing Changes

### 🧩 Syntax:

```bash
git checkout -- [file]
```

### 💡 Example:

```bash
git checkout -- app.js
# Discards local changes in app.js
```

---

### 🧩 Syntax:

```bash
git reset --hard [commit]
```

### 💡 Example:

```bash
git reset --hard a1b2c3d
# Resets repository to commit a1b2c3d
```

---

## 🧰 8. Stashing (Temporary Save)

### 🧩 Syntax:

```bash
git stash
```

### 💡 Example:

```bash
git stash
# Saves current changes temporarily
```

---

### 🧩 Syntax:

```bash
git stash list
```

### 💡 Example:

```bash
git stash list
# stash@{0}: WIP on main: Added form validation
```

---

### 🧩 Syntax:

```bash
git stash pop
```

### 💡 Example:

```bash
git stash pop
# Restores last stashed changes
```

---

## 🔍 9. Inspect and Compare

### 🧩 Syntax:

```bash
git log
```

### 💡 Example:

```bash
git log --oneline
# e1a35f7 Added login validation
# 2f94a6b Created login UI
```

---

### 🧩 Syntax:

```bash
git diff
```

### 💡 Example:

```bash
git diff
# Shows what’s changed but not yet staged
```

---

### 🧩 Syntax:

```bash
git diff --staged
```

### 💡 Example:

```bash
git diff --staged
# Shows differences between staged and committed code
```

---

## 🚫 10. Ignoring Files

### 🧩 Syntax:

```
# .gitignore
[patterns]
```

### 💡 Example:

```
node_modules/
.env
*.log
```

---

## 🔁 11. Rebase and Rewriting History

### 🧩 Syntax:

```bash
git rebase [branch]
```

### 💡 Example:

```bash
git rebase main
# Moves commits to start on top of main branch
```

---

### 🧩 Syntax:

```bash
git commit --amend -m "[new message]"
```

### 💡 Example:

```bash
git commit --amend -m "Updated commit message"
```

---

## 🧩 12. Practical Workflow Example

```bash
# Clone the repository
git clone https://github.com/shubhverma/app.git

# Create new branch
git checkout -b feature/ui

# Add and commit changes
git add .
git commit -m "Added UI components"

# Push to GitHub
git push origin feature/ui

# Merge with main
git checkout main
git merge feature/ui
```

---

Would you like me to **generate this guide as a styled PDF** (with color headers, boxes for syntax vs example, and Git logo) so you can print or share it?
