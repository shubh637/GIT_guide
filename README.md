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

* Always merge **feature branches into main** after review.
* Resolve conflicts manually if they arise.
  
### 🧩 Rebase Branch onto Another Branch

Syntax:
```bash
git rebase [branch]           # Rebase current branch onto [branch]
git rebase [upstream] [branch]  # Rebase [branch] onto [upstream] branch
git rebase -i [commit]        # Interactive rebase from specific commit
```
Example:
```bash
git checkout feature/ui
git rebase main
# Moves commits from feature/ui on top of main branch

git rebase -i HEAD~3
# Opens interactive rebase editor for last 3 commits
```
Usage Notes:

Use rebase to update your feature branch with the latest changes from main before merging.
-i (interactive) lets you edit, squash, or reorder commits.

🧩 Continue Rebase After Conflict

Syntax:
```bash
git add [file]          # Stage resolved files
git rebase --continue   # Continue rebase process
git rebase --abort      # Cancel rebase and go back
```

Example:
```bash
git add index.html
git rebase --continue

# If you decide to cancel rebase
git rebase --abort
```

Notes:

Conflicts may appear if the same lines were changed in both branches.
Always resolve conflicts before continuing.

---

1. **Rebase vs Merge:**

   * Merge preserves all commit history as a “merge commit.”
   * Rebase creates a **linear history** by moving your commits on top of main.

2. **When to rebase:**

   * Before merging a feature branch to main to **avoid messy merge commits**.
   * To **update your branch** with the latest changes from main.

3. **Force push after rebase:**

   * Rebasing rewrites history. If your branch was already pushed, you must use `git push -f`.

---

If you want, I can **also create a visual diagram of this workflow**, showing **branch creation, commits, rebasing, and merging**, which makes it very clear for beginners and teams.

Do you want me to make that diagram?


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

The `git reset` command is used to **move the HEAD to a specific commit**, optionally modifying the **staging area** and **working directory**. It is often used to undo mistakes in commits, unstage files, or discard changes.

---

**Syntax:**

```bash
git reset [file]             # Unstage a specific file
git reset --soft [commit]    # Undo commits but keep changes staged
git reset --mixed [commit]   # Undo commits and unstage changes (default)
git reset --hard [commit]    # Undo commits and discard all changes
```

---

**Examples:**

```bash
# 1️⃣ Unstage a file (keep local changes)
git reset index.html

# 2️⃣ Undo last commit but keep changes staged
git reset --soft HEAD~1

# 3️⃣ Undo last commit and unstage changes (default is mixed)
git reset --mixed HEAD~1

# 4️⃣ Undo last commit and discard all changes
git reset --hard HEAD~1

# 5️⃣ Reset branch to a specific commit and discard everything after
git reset --hard a1b2c3d
```

---

**Detailed Explanation:**

| Variant                      | What it does                                                                                  | Usage Example              | Safety         |
| ---------------------------- | --------------------------------------------------------------------------------------------- | -------------------------- | -------------- |
| `git reset [file]`           | Removes the file from staging but keeps changes in working directory                          | `git reset index.html`     | ✅ Safe         |
| `git reset --soft [commit]`  | Moves HEAD to the specified commit, **keeps changes staged**                                  | `git reset --soft HEAD~1`  | ✅ Safe         |
| `git reset --mixed [commit]` | Moves HEAD to the commit, **unstages changes**, working directory remains                     | `git reset --mixed HEAD~1` | ✅ Safe         |
| `git reset --hard [commit]`  | Moves HEAD to the commit, **clears staging area and working directory**, **all changes lost** | `git reset --hard a1b2c3d` | ⚠️ Destructive |

---

**Notes:**

1. `--mixed` is the **default mode** if no option is specified.
2. `--soft` is useful to **rewrite the last commit** or **combine commits**.
3. `--hard` is destructive — use **carefully**, especially if your changes aren’t backed up.
4. You can recover lost commits after a hard reset using:

```bash
git reflog
git checkout [commit-hash]
```
---
Example:
```bash
git reflog
# Output example:
# a1b2c3d (HEAD -> main) HEAD@{0}: commit: Added UI components
# 4d5e6f7 HEAD@{1}: commit: Fixed login bug
# 8g9h0i1 HEAD@{2}: reset: moving to HEAD~1

# 2️⃣ Checkout a lost commit to inspect or restore it
git checkout 4d5e6f7
# Now your working directory matches the commit "Fixed login bug"
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
Absolutely! Let’s make a **clear step-by-step guide** for restoring your local Git repository to exactly match the remote repository, with examples. This is especially useful if your local repo got messy after fetch, merge, or accidental changes.

---


## **Scenario**

You have a local repository, and after some changes or fetch, it looks different. You want it to be **exactly like the remote** (`origin/main`) again.

## **✅ Summary Command Sequence**

```bash
cd /path/to/repo
git fetch origin
git reset --hard origin/main
git clean -fd  # optional
git status
```

---

### **Example Use Case**

* Local repo: `~/Projects/MyApp`
* Remote repo: `git@github.com:shubh123/MyApp.git`
* You did some experimental changes that you don’t need.

**Commands to restore exactly:**

```bash
cd ~/Projects/MyApp
git fetch origin
```
What it does:
Updates information about the remote repo (origin/main)
Does not change your files yet
```bash
git reset --soft origin/main
```
What it does:
Makes your local main branch exactly like origin/main
All local commits and changes are discarded

```bash
git clean -fd
```
What it does(Optional):
Deletes untracked files (new files not added to Git)
Deletes untracked directories

```bash
git status
```

Your repo is now **exactly like GitHub**.




