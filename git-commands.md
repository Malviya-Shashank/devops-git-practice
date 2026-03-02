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
- `git branch <name>` — Create a new branch with the specified name.
- `git checkout <branch>` — Switch from the current branch to another.
- `git checkout -b <name>` — Create a new branch and switch to it immediately.
- `git switch <branch>` — The modern way to switch between existing branches.
- `git branch -d <name>` — Delete a branch that has already been merged.

## 🌐 Remote Repositories (GitHub)
- `git remote add origin <url>` — Link your local repository to a remote repository on GitHub.
- `git remote -v` — List all remote connections and their URLs.
- `git remote set-url origin <url>` — Change or update the URL of the remote "origin".
- `git push -u origin <branch>` — Push local commits to GitHub and set the upstream tracking.
- `git pull` — Fetch and integrate changes from the remote repository into your local branch.
- `git fetch` — Download objects and refs from another repository without merging them.

---

## 📜 Git Commands Table Summary

| Category | Command | Description |
| :--- | :--- | :--- |
| **Setup** | `git init` | Initializes a new local Git repository. |
| **Status** | `git status` | Shows the state of the working directory and staging area. |
| **Staging** | `git add <file>` | Adds changes to the staging area. |
| **Undo** | `git restore --staged <file>` | Removes a file from the staging area. |
| **Commit** | `git commit -m "msg"` | Saves staged changes as a new commit. |
| **History** | `git log` | Displays the commit history. |

---
*Last Updated: 2026-03-02*
