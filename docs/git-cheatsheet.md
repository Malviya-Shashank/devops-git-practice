# Git Cheatsheet

Quick reference for all Git commands covered in Days 22–26.

---

## Setup & Config

```bash
git version                                  # Check Git version
git config --global user.name "your-name"   # Set username
git config --global user.email "you@email"  # Set email
git init                                     # Initialize a new repo
```

---

## Core Workflow

```bash
git status                    # Check working tree state
git add <file>                # Stage a specific file
git add .                     # Stage all changes
git commit -m "message"       # Commit staged changes
git log                       # Full commit history
git log --oneline             # Compact commit history
git log --oneline --graph --all  # Visual branch graph
git diff                      # Show unstaged changes
```

---

## Branching

```bash
git branch                    # List local branches
git branch <name>             # Create a new branch
git switch <branch>           # Switch to a branch
git checkout -b <name>        # Create + switch in one step
git branch -d <name>          # Delete a branch (safe)
git branch -D <name>          # Force delete a branch
```

---

## Merging & Rebasing

```bash
git merge <branch>            # Merge branch into current
git merge --squash <branch>   # Squash all commits into one
git rebase <branch>           # Reapply commits on top of branch
git rebase --abort            # Cancel an in-progress rebase
```

---

## Undo & Fix

```bash
git restore --staged <file>   # Unstage a file
git reset --soft HEAD~1       # Undo commit, keep changes staged
git reset --mixed HEAD~1      # Undo commit, keep changes unstaged
git reset --hard HEAD~1       # Undo commit, DELETE changes ⚠️
git revert <hash>             # Safe undo — creates new commit
git reflog                    # View all HEAD movements (safety net)
```

---

## Stash

```bash
git stash                          # Stash current changes
git stash push -m "description"    # Stash with a label
git stash list                     # List all stashes
git stash pop                      # Apply + remove latest stash
git stash apply stash@{0}          # Apply specific stash (keep it)
git stash drop stash@{0}           # Delete a specific stash
```

---

## Cherry Pick

```bash
git cherry-pick <hash>        # Apply a specific commit to current branch
```

---

## Remote (GitHub)

```bash
git remote add origin <url>         # Link to remote repo
git remote -v                       # List remotes
git remote set-url origin <url>     # Update remote URL
git push -u origin <branch>         # Push + set upstream
git push                            # Push to tracked remote
git pull                            # Fetch + merge from remote
git fetch                           # Fetch only (no merge)
git clone <url>                     # Clone a remote repo locally
```

---

## GitHub CLI (`gh`)

```bash
gh auth login                        # Authenticate with GitHub
gh auth status                       # Check auth status
gh repo create <name> --public       # Create a new repo
gh repo clone <owner>/<repo>         # Clone a repo
gh repo list                         # List your repos
gh repo view --web                   # Open repo in browser

gh issue create --title "..." --body "..."   # Create an issue
gh issue list                                # List open issues
gh issue close <number>                      # Close an issue

gh pr create --fill                  # Create a PR
gh pr list                           # List open PRs
gh pr merge <number> --squash        # Merge a PR (squash)
gh pr review <number> --approve      # Approve a PR

gh run list                          # List workflow runs
gh workflow run "CI Pipeline"        # Trigger a workflow
gh release create v1.0.0             # Create a release
```

---

## Quick Decision Guide

| Situation | Command |
|---|---|
| Undo local commit (keep changes) | `git reset --soft HEAD~1` |
| Undo pushed commit safely | `git revert <hash>` |
| Save work temporarily | `git stash` |
| Apply one commit from another branch | `git cherry-pick <hash>` |
| Clean feature branch history | `git merge --squash` |
| Linear history before PR | `git rebase main` |
| Recover lost commits | `git reflog` |

---

## Reset vs Revert

| | `git reset` | `git revert` |
|---|---|---|
| Removes commit from history | Yes | No |
| Safe for shared branches | No | Yes |
| Rewrites history | Yes | No |
| Use when | Local cleanup | Shared/production branches |

---

## Branching Strategies

| Strategy | Best For |
|---|---|
| GitFlow | Large teams, scheduled releases |
| GitHub Flow | SaaS, continuous deployment |
| Trunk-Based | High-performance CI/CD teams |
