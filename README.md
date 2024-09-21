# Git Commands Cheat Sheet

This cheat sheet provides a quick reference to commonly used Git commands.

## Basic Commands

| Command                            | Description                                         |
|------------------------------------|-----------------------------------------------------|
| `git init`                         | Initialize a new Git repository.                   |
| `git clone <repo>`                 | Clone a repository into a new directory.           |
| `git status`                       | Show the working tree status.                       |
| `git add <file>`                   | Add a file to the staging area.                    |
| `git add .`                        | Stage all changes in the current directory.        |
| `git commit -m "message"`          | Commit changes to the repository with a message.   |
| `git commit -a -m "message"`       | Stage and commit changes to tracked files.          |
| `git log`                          | View the commit history.                            |
| `git log --oneline`               | View commit history in a condensed format.         |
| `git log --graph`                 | Visualize the commit history as a graph.           |
| `git diff`                         | Show changes between commits, working tree, etc.   |
| `git diff <commit1> <commit2>`    | Show changes between two commits.                   |

## Branching

| Command                             | Description                                         |
|-------------------------------------|-----------------------------------------------------|
| `git branch`                        | List all branches in the repository.               |
| `git branch <branch-name>`          | Create a new branch.                               |
| `git checkout <branch-name>`        | Switch to a branch.                                |
| `git checkout -b <branch-name>`     | Create and switch to a new branch.                 |
| `git merge <branch-name>`           | Merge a branch into the current branch.            |
| `git branch -d <branch-name>`       | Delete a branch (fails if the branch has unmerged changes). |
| `git branch -D <branch-name>`       | Force delete a branch.                             |
| `git rebase <branch-name>`          | Reapply commits on top of another base tip.       |

## Remote Repositories

| Command                               | Description                                         |
|---------------------------------------|-----------------------------------------------------|
| `git remote -v`                      | List remote repositories.                           |
| `git remote add <name> <url>`        | Add a new remote repository.                        |
| `git fetch <remote>`                 | Fetch changes from the remote repository.          |
| `git pull <remote> <branch>`          | Fetch and merge changes from the remote branch.    |
| `git push <remote> <branch>`          | Push changes to the remote repository.             |
| `git push origin --delete <branch>`   | Delete a remote branch.                            |
| `git remote show <remote>`           | Show detailed information about a remote.          |

## Stashing Changes

| Command                              | Description                                         |
|--------------------------------------|-----------------------------------------------------|
| `git stash`                          | Stash changes in a dirty working directory.        |
| `git stash list`                    | List stashed changes.                              |
| `git stash apply`                   | Apply stashed changes to the working directory.    |
| `git stash drop`                    | Remove a specific stash.                           |
| `git stash clear`                   | Clear all stashed changes.                         |
| `git stash pop`                     | Apply the most recent stash and remove it from the stash list. |

## Viewing Changes

| Command                               | Description                                         |
|---------------------------------------|-----------------------------------------------------|
| `git show <commit>`                  | Show changes made in a specific commit.            |
| `git blame <file>`                   | Show what revision and author last modified each line of a file. |
| `git log --stat`                     | Show changes made in each commit with stats.      |
| `git diff --cached`                  | Show changes staged for the next commit.          |

## Undoing Changes

| Command                               | Description                                         |
|---------------------------------------|-----------------------------------------------------|
| `git checkout -- <file>`             | Discard changes in the working directory.          |
| `git reset <file>`                   | Unstage a file while retaining changes.            |
| `git reset --hard`                   | Reset the working directory and index to the last commit. |
| `git reset HEAD~1`                   | Undo the last commit, keeping changes in the working directory. |

## Tagging

| Command                               | Description                                         |
|---------------------------------------|-----------------------------------------------------|
| `git tag`                            | List all tags.                                     |
| `git tag <tag-name>`                 | Create a new tag.                                  |
| `git tag -a <tag-name> -m "message"` | Create an annotated tag with a message.            |
| `git push origin <tag-name>`         | Push a tag to the remote repository.               |
| `git push --tags`                    | Push all tags to the remote repository.            |

## Help

| Command                               | Description                                         |
|---------------------------------------|-----------------------------------------------------|
| `git help`                           | Show help information about Git commands.          |
| `git <command> --help`               | Show help for a specific command.                  |

---

