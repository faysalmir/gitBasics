# Basic Git Flow for GitHub

A beginner-friendly guide to clone a GitHub repo, commit changes, push to GitHub, and pull updates.

---

## 1. One-Time Setup

Tell Git who you are:

```bash
git config --global user.name "Your Name"
git config --global user.email "your.email@example.com"
```

---

## 2. Clone a Repository

Download a GitHub repo to your computer:

```bash
git clone https://github.com/username/repository-name.git
```

Then move into the project folder:

```bash
cd repository-name
```

---

## 3. Daily Workflow: Add, Commit, Push

### Step 1: Check what changed

```bash
git status
```

### Step 2: Stage files

Stage one file:

```bash
git add filename.txt
```

Stage all changed files:

```bash
git add .
```

### Step 3: Commit changes

Save a snapshot locally with a message:

```bash
git commit -m "Your descriptive message here"
```

Example:

```bash
git commit -m "Fixed the login button bug"
```

### Step 4: Push to GitHub

Upload your commit to GitHub:

```bash
git push origin main
```

> Note: `origin` is the remote repository name. `main` is the branch name. Older repos may use `master`.

---

## 4. Pull Updates

If someone else changed the code on GitHub, get the latest changes:

```bash
git pull origin main
```

Always pull before starting new work to avoid conflicts.

---

## Quick Cheat Sheet

| Action | Command |
| :--- | :--- |
| Download a repo | `git clone <url>` |
| See changed files | `git status` |
| Stage all changes | `git add .` |
| Save changes locally | `git commit -m "message"` |
| Upload to GitHub | `git push origin main` |
| Download latest changes | `git pull origin main` |

---

## Typical Session Example

1. Pull latest changes:

```bash
git pull origin main
```

2. Edit your files in a code editor.

3. Check status:

```bash
git status
```

4. Stage changes:

```bash
git add .
```

5. Commit changes:

```bash
git commit -m "Updated readme"
```

6. Push to GitHub:

```bash
git push origin main
```

---

## Summary

The basic Git flow is:

```text
Clone → Edit → Add → Commit → Push
```

And when you need updates:

```text
Pull → Edit → Add → Commit → Push
```