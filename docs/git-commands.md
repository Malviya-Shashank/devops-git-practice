# Git Commands Reference Guide

This is a living document of the Git commands learned during the **#90DaysOfDevOps** challenge.

---

## 🛠️ Setup & Configuration
- `git version` — Check the current installed version of Git.
- `git config --global user.name "shashankmalv"` — Set your commit username.
- `git config --global user.email "malviyashashank7@gmail.com"` — Set your commit email.
- `git init` — Initialize a new local Git repository in the current folder.

## 📂 Basic Workflow
- `git status` — Check the state of the working directory and staging area.
- `git add <file>` — Add a specific file to the staging area.
- `git add .` — Add all new and changed files in the directory to the staging area.
- `git commit -m "message"` — Save staged changes to the repository history with a message.
- `git log` — View the full commit history of the current branch.
- `git restore --staged <file>` — Unstage a file while keeping its local changes.

## 🌿 Branching & Merging
- `git branch` — List all local branches in the repository.
- `git checkout -b <name>` — Create a new branch and switch to it immediately.
- `git switch <branch>` — The modern way to switch between existing branches.
- `git merge <branch>` — Combine changes from another branch into the current one.
- `git merge --squash <branch>` — Combine all commits from a branch into one single commit.
- `git rebase <branch>` — Reapply commits on top of another base tip for a linear history.

## ⚡ Advanced Workflows & Undo
- `git stash` — Temporarily shelve (stash) changes not yet ready to be committed.
- `git stash pop` — Remove the most recent stash and apply it to the working directory.
- `git cherry-pick <commit-hash>` — Apply the changes of a specific commit to the current branch.
- `git reset --soft HEAD~1` — Undo last commit; keep changes staged.
- `git reset --mixed HEAD~1` — Undo last commit; keep changes unstaged (default).
- `git reset --hard HEAD~1` — Undo last commit and permanently delete all changes.
- `git revert <commit-hash>` — Create a new commit that reverses the changes of a previous one.
- `git reflog` — View a record of every time the HEAD was moved (the ultimate safety net).

## 🌐 Remote Repositories (GitHub)
- `git remote add origin <url>` — Link your local repository to a remote repository on GitHub.
- `git remote -v` — List all remote connections and their URLs.
- `git remote set-url origin <ssh-url>` — Change the remote URL to use SSH (e.g., `git@github.com:user/repo.git`).
- `git push -u origin <branch>` — Push local commits to GitHub and set the upstream tracking.
- `git pull` — Fetch and integrate changes from the remote repository into your local branch.

---

## 📜 Git Commands Table Summary

| Category | Command | Description |
| :--- | :--- | :--- |
| **Undo (Local)** | `git reset` | Moves branch pointer back; rewrites local history. |
| **Undo (Public)** | `git revert` | Safely undoes changes by adding a new "inverse" commit. |
| **Safety Net** | `git reflog` | Recovers lost commits or resets even after a --hard reset. |
| **Remote** | `git remote set-url` | Updates the remote repository URL (SSH/HTTPS). |
| **Cleanup** | `git merge --squash` | Condenses feature branch history into one commit. |

---
*Last Updated: 2026-03-03*
