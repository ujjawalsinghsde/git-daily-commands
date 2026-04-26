# 🚀 Essential Git Commands for Daily Use

Your daily companion for Git workflows! This guide covers the commands you'll use 100+ times a week as a developer.

---

## ⚙️ Git Configuration

**Set up Git on your machine (do this once!):**

```bash
# 👤 Store your identity in every commit
git config --global user.name "Your Name"
git config --global user.email "your.email@example.com"

# 📝 Open commits in your favorite editor (VS Code, Vim, etc.)
git config --global core.editor "code --wait"

# 🎨 Pretty colors for easier reading
git config --global color.ui auto
```

---

## 📚 Basic Commands

```bash
# 🎬 Create a new Git repository in current folder
git init

# 📦 Download an entire project from remote
git clone <repository-url>

# 👀 Check what's changed: modified, staged, untracked files
git status

# 📖 View full commit history (messages + diffs)
git log

# 📝 View commits in one-line format (faster to scan)
git log --oneline

# 🌳 Visualize commit history with branches as a graph (my favorite!)
git log --oneline --graph --all
```

---

## 📂 Working with Files

```bash
# ✅ Stage specific file(s) to be committed
git add <file-or-directory>

# ⭐ Stage all modified files at once (time-saver!)
git add .

# 🗑️ Remove file from project and stage the deletion
git rm <file>

# ✏️ Rename/move a file and automatically stage it
git mv <old-filename> <new-filename>

# 🔄 Undo changes to a file (restore from last commit)
git restore <file>

# 👀 See exactly what changed in a file
git diff <file>
```

---

## 💾 Committing Changes

```bash
# 📌 Save staged changes with a descriptive message
git commit -m "Add user authentication feature"

# ⚡ Stage & commit all changes in one command (skips `git add`)
git commit -a -m "Fix login bug"

# 🔧 Oops! Fix the message or add forgotten files to last commit
git commit --amend

# ✍️ Add your signature to commits (useful for open source)
git commit -s -m "Improve performance"

# 📋 Write detailed commit message in editor
git commit  # Opens your default editor for multi-line messages
```

---

## 🌿 Branching

```bash
# 📋 See all branches (local branches only)
git branch

# 🆕 Create a new branch (doesn’t switch to it)
git branch <branch-name>

# 🔀 Switch to an existing branch
git checkout <branch-name>

# ⚡ Create AND switch to a new branch in one command
git checkout -b <branch-name>

# 🧹 Delete a branch (local, only if fully merged)
git branch -d <branch-name>

# 🚨 Force delete a branch (USE WITH CAUTION!)
git branch -D <branch-name>

# 📍 Show your current branch name
git branch --show-current

# 🔄 Switch to branch using shorter syntax (Git 2.23+)
git switch <branch-name>

# ⚡ Create and switch with newer syntax (Git 2.23+)
git switch -c <branch-name>
```

---

## 🔗 Merging & Rebasing

```bash
# 🤝 Merge another branch into current branch
git merge <branch-name>

# 📚 Rebase current branch on top of another (cleaner history!)
git rebase <branch-name>

# ✅ Continue rebase after fixing conflicts
git rebase --continue

# ❌ Abort rebase if it's too messy
git rebase --abort

# 🎯 Interactive rebase - squash/rename/reorder commits
git rebase -i <commit-id>

# 🔀 Merge with a merge commit (even if fast-forward possible)
git merge --no-ff <branch-name>
```

---

## 📦 Stashing (Temporary Storage)

```bash
# 💾 Save work-in-progress without committing (cleans your workspace)
git stash

# 📝 Save stash with a descriptive name
git stash save "WIP: fixing login bug"

# 📂 List all saved stashes
git stash list

# 🔙 Apply latest stash and remove it from list
git stash pop

# 📌 Apply stash but keep it in list
git stash apply stash@{0}

# 🗑️ Delete a specific stash
git stash drop stash@{0}

# 🧹 Delete all stashes
git stash clear
```

---

## 🌐 Remote Repositories

```bash
# 🔗 Add a new remote connection (usually called 'origin')
git remote add origin <repository-url>

# 👀 See all remote connections and their URLs
git remote -v

# 📥 Download new changes from remote (doesn't merge yet)
git fetch

# 📥 Download and automatically merge remote changes
git pull origin <branch-name>

# 📥 Pull with rebase (cleaner history, no merge commits)
git pull --rebase origin <branch-name>

# 📤 Upload your commits to remote
git push origin <branch-name>

# 📤 Push all branches to remote
git push --all origin

# 🏷️ Push tags to remote
git push --tags

# 🗑️ Delete a branch on remote
git push origin --delete <branch-name>

# 🔍 See remote branch details
git remote show origin
```

---

## ↩️ Undoing Changes

```bash
# 🔄 Discard changes in a file (restore from last commit)
git checkout -- <file>

# 🔄 Remove file from staging area (but keep your changes)
git restore --staged <file>

# ↩️ Unstage a file without losing your work
git reset <file>

# 🚨 HARD RESET: Delete all changes and go back to commit (DANGEROUS!)
git reset --hard <commit-id>

# 💾 Soft reset: Keep changes but undo commits
git reset --soft <commit-id>

# ↪️ Create a new commit that undoes another commit (safe way!)
git revert <commit-id>

# 🔍 See what was in a deleted commit
git reflog  # Shows your recent actions (lifesaver!)
```

---

## 🏷️ Tagging (Versions & Releases)

```bash
# 📋 List all tags (versions/releases in your project)
git tag

# 🏷️ Create a simple tag (lightweight)
git tag <tag-name>

# 🏷️ Create an annotated tag with description
git tag -a <tag-name> -m "Release v1.0"

# 🔍 Show details of a tag
git show <tag-name>

# 📤 Push a specific tag to remote
git push origin <tag-name>

# 📤 Push ALL tags at once
git push origin --tags

# 🗑️ Delete a local tag
git tag -d <tag-name>

# 🗑️ Delete a tag on remote
git push origin --delete <tag-name>
```

---

## ⚡ Helpful Shortcuts & Hidden Gems

```bash
# 📊 Compact status (easier to scan than `git status`)
git status -s

# 📝 See what changed in current branch
git diff

# 📝 See changes ready to commit
git diff --cached

# 🔍 Show full details of latest commit
git show

# 🔍 Show changes from a specific commit
git show <commit-id>

# 📄 See which files Git is ignoring
git check-ignore *

# 🧹 Delete untracked files (test carefully!)
git clean -f

# 🧹 Delete untracked files AND directories
git clean -fd

# 🔎 Search commit messages for a keyword
git log --grep="fix"

# 👤 See commits by a specific author
git log --author="name"

# 📊 Show stats: files changed, insertions/deletions
git log --stat

# 🎯 Find which commit introduced a bug (binary search)
git bisect start

# 🔗 Cherry-pick: Apply specific commit to current branch
git cherry-pick <commit-id>

# 🔀 Show which branches contain a specific commit
git branch -r --contains <commit-id>

# 📌 See what's in a commit without checking it out
git show <commit-id>:<file-path>
```

---

## 🛠️ Real-World Workflows (Daily Scenarios)

### Scenario 1️⃣: Start a New Feature

You're starting fresh on a new feature. Here's your workflow:

```bash
# Get latest code from main branch
git checkout main
git pull origin main

# Create your feature branch
git checkout -b feature/dark-mode
```

### Scenario 2️⃣: Make Changes & Commit

You've written some code. Now save it:

```bash
# Check what you changed
git status

# Stage your changes
git add .

# Save with a clear message
git commit -m "Add dark mode toggle to settings"
```

### Scenario 3️⃣: Keep Your Branch Updated

Main branch got new commits. Catch up:

```bash
# Get latest code from main
git fetch origin main

# Rebase your work on top (clean history)
git rebase origin/main

# If conflicts happen, fix them and continue
# git rebase --continue
```

### Scenario 4️⃣: Push & Create Pull Request

Ready to share your work:

```bash
# Upload your branch
git push origin feature/dark-mode

# Now go to GitHub/GitLab and create a Pull Request (PR)
```

### Scenario 5️⃣: Merge & Clean Up

PR approved! Merge and clean:

```bash
# Delete branch locally
git branch -d feature/dark-mode

# Delete branch on remote
git push origin --delete feature/dark-mode
```

### 🆘 Scenario 6️⃣: Oops! I Made a Mistake

**Forgot to stage a file before committing?**
```bash
git add forgotten-file.js
git commit --amend
```

**Committed to wrong branch?**
```bash
git reset --soft HEAD~1  # Undo commit, keep changes
git checkout correct-branch
git commit -m "message"
```

**Pushed bad code to main?** (Real situation! 😅)
```bash
git revert <bad-commit-id>  # Creates a new commit that undoes it
git push origin main
```

**Lost commits?**
```bash
git reflog  # Shows your history (lifesaver!)
git checkout <lost-commit-id>
```

---

## 💡 Pro Tips

✅ **Do this:**
- ✍️ Write clear commit messages (future-you will thank you)
- 🌿 Create feature branches, don't commit to main
- 📥 Pull regularly to stay in sync with team
- 🧪 Test before pushing
- 📚 Use meaningful branch names: `feature/`, `bugfix/`, `hotfix/`

❌ **Don't do this:**
- 🚨 Force push to shared branches (`git push -f`)
- 💀 Use `git reset --hard` unless 100% sure
- 📝 Commit to main directly (use branches!)
- 🔀 Large commits mixing multiple features (keep commits focused)
- 🤐 Unclear commit messages like "fix stuff" or "update"

---

## 🔗 Helpful Resources

- [Git Official Docs](https://git-scm.com/doc)
- [GitHub Guides](https://guides.github.com/)
- [Atlassian Git Tutorials](https://www.atlassian.com/git/tutorials)

---

## ❓ Quick Reference Card

| Task | Command |
|------|---------|
| See what changed | `git status` |
| Create branch | `git checkout -b <name>` |
| Stage files | `git add .` |
| Commit | `git commit -m "msg"` |
| Push | `git push origin <branch>` |
| Pull | `git pull origin <branch>` |
| Undo last commit | `git reset --soft HEAD~1` |
| View history | `git log --oneline --graph --all` |
| Save for later | `git stash` |
| Merge branches | `git merge <branch>` |

---

**Happy coding! 🎉 Make great commits!**
