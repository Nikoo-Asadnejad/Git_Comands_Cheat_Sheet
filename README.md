# Git Commands Cheat Sheet

This cheat sheet provides a quick reference to commonly used Git commands, from beginner to advanced.

---

# Basic Commands

| Command | Description |
|---------|-------------|
| `git init` | Initialize a new Git repository. |
| `git clone <repo>` | Clone a repository. |
| `git status` | Show working tree status. |
| `git add <file>` | Stage a file. |
| `git add .` | Stage all changes. |
| `git add -p` | Interactively stage parts of files. |
| `git commit -m "message"` | Commit staged changes. |
| `git commit -a -m "message"` | Stage tracked files and commit. |
| `git commit --amend` | Modify the previous commit. |
| `git commit --amend --no-edit` | Add staged changes to the previous commit without changing its message. |
| `git log` | View commit history. |
| `git log --oneline` | Compact commit history. |
| `git log --graph --all --decorate` | Visualize the complete commit graph. |
| `git diff` | Show unstaged changes. |
| `git diff --cached` | Show staged changes. |
| `git diff HEAD` | Show all changes since last commit. |
| `git diff <commit1> <commit2>` | Compare two commits. |
| `git shortlog -sn` | Show commit counts per contributor. |

---

# Branching

| Command | Description |
|---------|-------------|
| `git branch` | List branches. |
| `git branch -a` | List local and remote branches. |
| `git branch <branch>` | Create a branch. |
| `git checkout <branch>` | Switch branches. |
| `git checkout -b <branch>` | Create and switch to a branch. |
| `git switch <branch>` | Switch branches (modern alternative). |
| `git switch -c <branch>` | Create and switch to a new branch. |
| `git merge <branch>` | Merge a branch. |
| `git merge --no-ff <branch>` | Force a merge commit. |
| `git rebase <branch>` | Rebase onto another branch. |
| `git rebase -i HEAD~5` | Interactive rebase of the last 5 commits. |
| `git cherry-pick <commit>` | Apply a specific commit. |
| `git branch -d <branch>` | Delete a merged branch. |
| `git branch -D <branch>` | Force delete a branch. |
| `git branch -m <new-name>` | Rename current branch. |

---

# Remote Repositories

| Command | Description |
|---------|-------------|
| `git remote -v` | Show remotes. |
| `git remote add <name> <url>` | Add a remote. |
| `git remote remove <name>` | Remove a remote. |
| `git remote rename <old> <new>` | Rename a remote. |
| `git remote show <remote>` | Show remote details. |
| `git fetch` | Fetch all remotes. |
| `git fetch --all --prune` | Fetch all remotes and remove deleted remote branches. |
| `git pull` | Fetch and merge. |
| `git pull --rebase` | Fetch and rebase instead of merge. |
| `git push` | Push current branch. |
| `git push -u origin <branch>` | Push and set upstream branch. |
| `git push --force-with-lease` | Safer force push. |
| `git push origin --delete <branch>` | Delete remote branch. |

---

# Git Worktrees

Git Worktrees allow you to work on multiple branches simultaneously without creating multiple clones.

| Command | Description |
|---------|-------------|
| `git worktree list` | List all worktrees. |
| `git worktree add ../feature feature-branch` | Create a worktree for an existing branch. |
| `git worktree add -b feature ../feature` | Create a new branch and worktree. |
| `git worktree remove ../feature` | Remove a worktree. |
| `git worktree prune` | Remove stale worktree metadata. |
| `git worktree lock` | Prevent a worktree from being pruned. |
| `git worktree unlock` | Unlock a worktree. |
| `git worktree repair` | Repair broken worktree metadata. |

### Example

```bash
git checkout main

git worktree add ../feature-login feature/login

cd ../feature-login

# main and feature/login are now open simultaneously
```

### Benefits

- Work on multiple branches simultaneously.
- No need to stash changes when switching tasks.
- Faster than cloning repositories.
- Great for code reviews and hotfixes.

---

# Stashing Changes

| Command | Description |
|---------|-------------|
| `git stash` | Stash current changes. |
| `git stash push -m "message"` | Stash with a message. |
| `git stash -u` | Include untracked files. |
| `git stash list` | List stashes. |
| `git stash show` | Show stash summary. |
| `git stash show -p` | Show full stash diff. |
| `git stash apply` | Apply a stash. |
| `git stash pop` | Apply and remove latest stash. |
| `git stash drop` | Delete a stash. |
| `git stash clear` | Delete all stashes. |

---

# Viewing Changes

| Command | Description |
|---------|-------------|
| `git show <commit>` | Show commit details. |
| `git show HEAD` | Show latest commit. |
| `git blame <file>` | Show line authorship. |
| `git log --stat` | Show commit statistics. |
| `git log --name-only` | Show modified files. |
| `git log --follow <file>` | Track file history across renames. |
| `git diff --word-diff` | Show word-level changes. |
| `git whatchanged` | Show changed files for each commit. |

---

# Undoing Changes

| Command | Description |
|---------|-------------|
| `git restore <file>` | Restore a file. |
| `git restore --staged <file>` | Unstage a file. |
| `git checkout -- <file>` | Discard changes (legacy). |
| `git reset <file>` | Unstage a file. |
| `git reset --soft HEAD~1` | Undo last commit and keep changes staged. |
| `git reset HEAD~1` | Undo last commit and keep changes unstaged. |
| `git reset --hard HEAD` | Reset everything to the latest commit. |
| `git revert <commit>` | Undo a commit with a new commit. |
| `git clean -fd` | Remove untracked files and directories. |
| `git clean -fdx` | Remove ignored files as well. |

---

# Tags

| Command | Description |
|---------|-------------|
| `git tag` | List tags. |
| `git tag <tag>` | Create a lightweight tag. |
| `git tag -a <tag> -m "message"` | Create an annotated tag. |
| `git show <tag>` | Show tag details. |
| `git push origin <tag>` | Push a tag. |
| `git push --tags` | Push all tags. |
| `git tag -d <tag>` | Delete a local tag. |
| `git push origin --delete <tag>` | Delete a remote tag. |

---

# Advanced Commands

| Command | Description |
|---------|-------------|
| `git reflog` | View all HEAD movements (excellent for recovering lost commits). |
| `git bisect start` | Start binary search for a bug. |
| `git bisect good` | Mark a commit as good. |
| `git bisect bad` | Mark a commit as bad. |
| `git bisect reset` | Finish bisect session. |
| `git cherry -v` | Show commits not yet merged upstream. |
| `git describe --tags` | Show the nearest tag to the current commit. |
| `git archive` | Create a ZIP/TAR archive of the repository. |
| `git fsck` | Verify repository integrity. |
| `git gc` | Optimize and clean the repository. |
| `git maintenance run` | Run Git maintenance tasks. |
| `git sparse-checkout init` | Enable sparse checkout. |
| `git sparse-checkout set <dir>` | Check out only selected directories. |
| `git submodule update --init --recursive` | Initialize and update submodules. |
| `git submodule foreach git pull` | Pull updates in all submodules. |

---

# Configuration

| Command | Description |
|---------|-------------|
| `git config --global user.name "Name"` | Set your username. |
| `git config --global user.email "email@example.com"` | Set your email. |
| `git config --list` | Display current configuration. |
| `git config --global alias.st status` | Create a Git alias. |
| `git config --global core.editor "code --wait"` | Set default editor. |
| `git config --global init.defaultBranch main` | Set default branch name. |

---

# Helpful Aliases

| Alias | Expands To |
|------|-------------|
| `git st` | `git status` |
| `git co` | `git checkout` |
| `git sw` | `git switch` |
| `git br` | `git branch` |
| `git ci` | `git commit` |
| `git lg` | `git log --graph --decorate --oneline --all` |
| `git last` | `git log -1 HEAD` |

### Configure aliases

```bash
git config --global alias.st status
git config --global alias.co checkout
git config --global alias.sw switch
git config --global alias.br branch
git config --global alias.ci commit
git config --global alias.last "log -1 HEAD"
git config --global alias.lg "log --graph --decorate --oneline --all"
```

---

# Help

| Command | Description |
|---------|-------------|
| `git help` | Show Git help. |
| `git <command> --help` | Show help for a specific command. |
| `git config --help` | Configuration documentation. |

---

# Professional Tips

- Use `git pull --rebase` to maintain a cleaner commit history.
- Use `git push --force-with-lease` instead of `--force`.
- Learn `git reflog`—it's one of Git's most valuable recovery tools.
- Use Git Worktrees to work on multiple branches simultaneously.
- Clean up your commit history with `git rebase -i` before opening a pull request.
- Use `git bisect` to quickly identify the commit that introduced a bug.
- Consider sparse checkout when working in very large monorepositories.
