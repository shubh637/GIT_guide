# 🧭 Complete Git Guide – Syntax, Examples, and Usage Notes

---

## ⚙️ 1. Git Setup

Before starting Git, you should set your identity.

### 🧩 Configure User Info

**Syntax:**

```bash
git config --global user.name "[your name]"
git config --global user.email "[your email]"
```

**Example:**

```bash
git config --global user.name "Shubh Verma"
git config --global user.email "shubh@example.com"
```

**Notes:**

* `--system` → Sets for all users on the machine
* `--global` → Sets for your user (common)
* `--local` → Sets for current repo only

---

### 🧩 View Git Configuration

**Syntax:**

```bash
git config --list
```

**Example:**

```bash
git config --list
# user.name=Shubh Verma
# user.email=shubh@example.com
```

---

## 🏁 2. Initialize or Clone a Repository

### 🧩 Initialize Git Repo

```bash
git init
```

**Example:**

```bash
git init
# Initialized empty Git repository in /myproject/.git/
```

**Usage:** Use this when creating a **new project** from scratch.

---

### 🧩 Clone Repository

```bash
git clone [url]
git clone [url] [folder-name]   # optional folder name
```

**Example:**

```bash
git clone https://github.com/shubhverma/weather-app.git
git clone https://github.com/shubhverma/weather-app.git my-app
# Clones repo into folder my-app
```

**Usage:** Use this when **copying an existing remote repo**.

---

## 📦 3. Staging and Committing

### 🧩 Check Status

```bash
git status
```

**Example:**

```bash
git status
# Shows modified, staged, and untracked files
```

**Usage:** Always check **what’s staged/untracked** before committing.

---

### 🧩 Stage Files

```bash
git add [file]       # Stage a single file
git add .            # Stage all changes in current directory
git add -p           # Stage parts of files interactively
```

**Example:**

```bash
git add index.html
git add .           # Stage everything
git add -p          # Stage changes selectively
```

**Notes:** Staging prepares files to commit. `git add -p` is useful for **partial commits**.

---

### 🧩 Commit Changes

```bash
git commit -m "[message]"
git commit -a -m "[message]"   # Stage tracked files and commit
git commit --amend -m "[message]"  # Amend previous commit
```

**Example:**

```bash
git commit -m "Added login feature"
git commit -a -m "Updated CSS styles"
git commit --amend -m "Corrected typo in last commit"
```

**Notes:**

* `-a` commits all **tracked files** without `git add`
* `--amend` modifies **last commit message** or adds missed files

---

## 🌿 4. Branching and Merging

### 🧩 List Branches

```bash
git branch
git branch -a   # Show all branches including remote
```

**Example:**

```bash
git branch
# * main
# feature/login
```

---

### 🧩 Create Branch

```bash
git branch [branch-name]
git checkout -b [branch-name]  # Creates and switches
```

**Example:**

```bash
git branch feature/payment       # Creates branch
git checkout -b feature/login    # Create + switch
```

---

### 🧩 Switch Branch

```bash
git checkout [branch-name]
git switch [branch-name]         # Newer, recommended
git switch -c [branch-name]      # Create + switch
```

**Example:**

```bash
git checkout feature/payment
git switch main
git switch -c feature/ui
```

---

### 🧩 Merge Branches

```bash
git merge [branch-name]
git merge --no-ff [branch-name]   # Force a merge commit
```

**Example:**

```bash
git merge feature/payment
git merge --no-ff feature/ui
```

**Notes:**

* Always merge **feature branches into main** after review.
* Resolve conflicts manually if they arise.

---

## 🔄 5. Remote Repositories

### 🧩 Add Remote

```bash
git remote add [alias] [url]
```

**Example:**

```bash
git remote add origin https://github.com/shubhverma/weather-app.git
```

---

### 🧩 Push Changes

```bash
git push [alias] [branch]
git push -u origin main      # Set upstream for future pushes
git push --force             # Overwrite remote branch (use cautiously)
```

**Example:**

```bash
git push origin main
git push -u origin feature/login
```

---

### 🧩 Pull Changes

```bash
git pull [alias] [branch]
```

**Example:**

```bash
git pull origin main
```

**Notes:** Fetches remote changes **and merges** automatically.

---

### 🧩 Fetch Changes

```bash
git fetch [alias]
```

**Example:**

```bash
git fetch origin
# Fetches remote changes without merging
```

---

## 🗂️ 6. File Changes

### 🧩 Rename Files

```bash
git mv [old-name] [new-name]
```

**Example:**

```bash
git mv oldfile.txt newfile.txt
```

---

### 🧩 Delete Files

```bash
git rm [file]
git rm --cached [file]   # Remove from Git but keep locally
```

**Example:**

```bash
git rm notes.txt
git rm --cached secret.txt
```

---

## 🧹 7. Undoing Changes

### 🧩 Discard Local Changes

```bash
git checkout -- [file]       # Unstaged changes
git restore [file]           # Newer alternative
```

**Example:**

```bash
git checkout -- app.js
git restore app.js
```

---

### 🧩 Reset Changes

```bash
git reset [file]             # Unstage file
git reset --hard [commit]    # Reset working directory and history
git reset --soft [commit]    # Reset history but keep changes staged
```

**Example:**

```bash
git reset index.html
git reset --hard a1b2c3d
git reset --soft HEAD~1
```

---

## 🧰 8. Stashing (Temporary Save)

### 🧩 Save Work Temporarily

```bash
git stash
git stash save "message"
```

**Example:**

```bash
git stash
git stash save "WIP: updating UI"
```

---

### 🧩 View Stashes

```bash
git stash list
git stash show [stash@{n}]
```

**Example:**

```bash
git stash list
# stash@{0}: WIP on main: updating UI
git stash show stash@{0}
```

---

### 🧩 Apply Stash

```bash
git stash apply [stash@{n}]
git stash pop
```

**Example:**

```bash
git stash apply stash@{0}
git stash pop
```

---

## 🔍 9. Inspect and Compare

### 🧩 View Commit History

```bash
git log
git log --oneline --graph --all --decorate
```

**Example:**

```bash
git log --oneline
# e1a35f7 Added login validation
# 2f94a6b Created login UI
```

---

### 🧩 Compare Changes

```bash
git diff                  # Unstaged changes
git diff --staged         # Staged changes
git diff [commit1] [commit2]  # Compare commits
```

**Example:**

```bash
git diff
git diff --staged
git diff HEAD~1 HEAD
```

---

## 🚫 10. Ignoring Files

**Syntax in `.gitignore`:**

```
# Ignore folders
node_modules/
# Ignore environment files
.env
# Ignore logs
*.log
```

---

## 🔁 11. Rebase and Rewrite History

### 🧩 Rebase Branch

```bash
git rebase [branch]
git rebase -i [commit]   # Interactive rebase
```

**Example:**

```bash
git rebase main
git rebase -i HEAD~3
```

---

### 🧩 Amend Commit

```bash
git commit --amend -m "[new message]"
```

**Example:**

```bash
git commit --amend -m "Updated commit message"
```

---

## 🧩 12. Practical Workflow Example

```bash
# Clone the repo
git clone https://github.com/shubhverma/app.git

# Create and switch to new branch
git checkout -b feature/ui

# Stage and commit changes
git add .
git commit -m "Added UI components"

# Push branch to remote
git push -u origin feature/ui

# Merge changes to main
git checkout main
git merge feature/ui
git push origin main
```

---




