# GIT CHEAT SHEET

---

## GIT BASICS
> Essential commands to initialize and manage local projects.

* **`git init <directory>`**
  - Create empty Git repo in specified directory. Run with no arguments to initialize the current directory.
* **`git clone <repo>`**
  - Clone repo located at `<repo>` onto local machine (HTTP or SSH supported).
* **`git status`**
  - List which files are staged, unstaged, and untracked.
* **`git add <file/directory>`**
  - Stage all changes in `<directory>` for the next commit (or a specific `<file>`).
* **`git commit -m "<message>"`**
  - Commit the staged snapshot using `<message>` as the commit message (bypasses text editor).

---

## GIT BRANCHES
> Manage and merge development timelines.

* **`git branch`**
  - List all of the branches in your repo. Add a `<branch>` argument to create a new branch.
* **`git checkout -b <branch>`**
  - Create and check out a new branch named `<branch>`. Drop the `-b` flag to checkout an existing branch.
* **`git merge <branch>`**
  - Merge `<branch>` into the current branch.

---

## REMOTE REPOSITORIES
> Collaboration and synchronizing with remote servers.

* **`git remote add <name> <url>`**
  - Create new connection to remote repo using `<name>` as shortcut for `<url>`.
* **`git fetch <remote> <branch>`**
  - Fetches a specific `<branch>` from the repo. Leave off `<branch>` to fetch all remote refs.
* **`git pull <remote>`**
  - Fetch the specified remote’s copy of the current branch and immediately merge it into the local copy.
* **`git push <remote> <branch>`**
  - Push the branch to `<remote>`, along with necessary commits/objects. Creates named branch in the remote repo if it doesn’t exist.
* **`git push <remote> --tags`**
  - Sends all of your local tags to the remote repo (tags aren't pushed automatically).
* **`git push <remote> --force`**
  - Forces the git push even if it results in a non-fast-forward merge. Do not use unless you are absolutely sure you know what you’re doing!
* **`git push <remote> --all`**
  - Push all of your local branches to the specified remote.

---

## UNDOING CHANGES & REWRITING HISTORY
> Correcting mistakes or restructuring commits.

* **`git reset <file>`**
  - Remove `<file>` from the staging area (unstage), but leave the working directory unchanged.
* **`git clean -n`**
  - Shows which files would be removed from the working directory. Use the `-f` flag to execute the clean.
* **`git revert <commit>`**
  - Create new commit that undoes all of the changes made in `<commit>`, then apply it to the current branch.
* **`git commit --amend`**
  - Replace the last commit with the staged changes and last commit combined. Use with nothing staged to edit the last commit’s message.
* **`git rebase <base>`**
  - Rebase the current branch onto `<base>`. `<base>` can be a commit ID, branch name, tag, or relative reference to HEAD.
* **`git rebase -i <base>`**
  - Interactively rebase current branch onto `<base>`. Launches editor to enter commands for how each commit will be transferred.

---

## GIT RESET MODES
> Resetting the state of your repository.



| Command | Effect |
| :--- | :--- |
| **`git reset`** | Reset staging area to match most recent commit, but leave the working directory unchanged. |
| **`git reset --hard`** | Reset staging area and working directory to match most recent commit, overwriting all changes. |
| **`git reset <commit>`** | Move the current branch tip backward to `<commit>`, reset the staging area to match, but leave the working directory alone. |
| **`git reset --hard <commit>`** | Resets both the staging area & working directory, deleting uncommitted changes and all commits after `<commit>`. |

---

## GIT LOG (INSPECTION)
> Reviewing the history of the project.

* **`git log --oneline`**
  - Condense each commit to a single line.
* **`git log --graph --decorate`**
  - Draws a text based graph of commits on the left side and adds names of branches/tags.
* **`git log --author="<pattern>"`**
  - Search for commits by a particular author.
* **`git log -<limit>`**
  - Limit number of commits by `<limit>` (e.g., `git log -5`).
* **`git log --grep="<pattern>"`**
  - Search for commits with a commit message that matches `<pattern>`.

---

## GIT CONFIG
> System-wide and project-specific settings.

```bash
# Define user identity
git config --global user.name <name>
git config --global user.email <email>

# Open global config for manual editing
git config --global --edit

# Create shortcuts/aliases
git config --global alias.<alias-name> <git-command>
