# 🛠️ GIT CHEAT SHEET

---

## 🚀 GIT BASICS
> Essential commands to start your project.

* `git init <directory>` 
  - Create empty Git repo in specified directory. Run with no args for current directory.
* `git clone <repo>` 
  - Clone repo onto local machine (HTTP or SSH).
* `git status` 
  - List files that are **staged**, **unstaged**, and **untracked**.
* `git add <file/dir>` 
  - Stage changes for the next commit.
* `git commit -m "<msg>"` 
  - Commit the staged snapshot with a custom message.

---

## 🌿 GIT BRANCHES
> Manage your development streams.

* `git branch` 
  - List all branches. Add a `<branch>` name to create a new one.
* `git checkout -b <branch>` 
  - Create and switch to a new branch immediately.
* `git merge <branch>` 
  - Merge the specified branch into your current one.

---

## 🌐 REMOTE REPOSITORIES
> Collaborating with external servers.

* `git remote add <name> <url>` 
  - Connect to a remote repo using a shortcut name.
* `git fetch <remote> <branch>` 
  - Pull down refs from the remote without merging.
* `git pull <remote>` 
  - Fetch and **immediately merge** remote changes into local.
* `git push <remote> <branch>` 
  - Upload local commits to the remote repository.
* `git push <remote> --force` 
  - ⚠️ **CAUTION:** Forces the push even if it overwrites remote history.

---

## ⏪ UNDOING & HISTORY
> Fixing mistakes and rewriting what happened.


| Action | Command | Effect |
| :--- | :--- | :--- |
| **Unstage** | `git reset <file>` | Removes file from staging; leaves directory alone. |
| **Undo Commit** | `git revert <commit>` | Creates a NEW commit that reverses changes. |
| **Fix Last** | `git commit --amend` | Combines staged changes with the previous commit. |
| **Rebase** | `git rebase <base>` | Re-applies commits on top of another base tip. |

---

## 🧹 GIT RESET (THE NUCLEAR OPTIONS)
> Use these to align your workspace with specific commits.

* `git reset --hard` 
  - Matches staging/directory to latest commit; **overwrites all changes**.
* `git reset --hard <commit>` 
  - Resets to a specific point, **deleting** all commits/changes after it.

---

## 📜 GIT LOG (INSPECTION)
> Finding out who did what and when.

* `git log --oneline` 
  - Condense history into single lines.
* `git log --graph --decorate` 
  - Visualizes branches and tags in a text-based graph.
* `git log --author="<name>"` 
  - Filter history by a specific contributor.

---

## ⚙️ GIT CONFIG
> Setup and shortcuts.

```bash
# Set Identity
git config --global user.name "<name>"
git config --global user.email "<email>"

# Create Shortcuts (Example: 'git glog' for a pretty graph)
git config --global alias.glog "log --graph --oneline"
