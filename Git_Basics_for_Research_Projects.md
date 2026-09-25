# Git Basics for Research Projects

This guide explains the basic Git operations used in a typical Python,
Jupyter, econometrics, or data-analytics research project.

## 1. The Basic Idea

Think of Git as connecting three places:

``` text
YOUR COMPUTER              GIT                     GITHUB
Working files      ->      Local repository   ->   Remote repository
                          (version history)
```

Your normal workflow is:

``` text
Edit files
    |
    v
git status
    |
    v
git add
    |
    v
git commit
    |
    v
git push
    |
    v
GitHub
```

A useful sequence to remember is:

**Pull -\> Work -\> Status -\> Add -\> Commit -\> Push**

------------------------------------------------------------------------

## 2. `git clone` - Get the Project for the First Time

``` bash
git clone https://github.com/faysalmir/Data-Analytics.git
```

Meaning:

> Make a complete local copy of this GitHub repository on my computer.

Normally, you clone a repository only once for each computer or working
location.

Example:

``` text
GitHub
   |
   | git clone
   v
D:\Research\Data-Analytics
```

------------------------------------------------------------------------

## 3. `git status` - Check What Has Changed

``` bash
git status
```

Meaning:

> Show me the current state of my project and tell me which files have
> changed.

This is one of the safest and most useful Git commands. Run it
frequently.

If Git reports:

``` text
modified: notebooks/psx_analysis.ipynb
```

the file is already tracked by Git but has been changed since the last
commit.

If Git reports:

``` text
Untracked files:
notebooks/new_analysis.ipynb
```

the file is new and has never been recorded by Git.

------------------------------------------------------------------------

## 4. `git add` - Select Changes for the Next Commit

To stage one file:

``` bash
git add notebooks/psx_analysis.ipynb
```

Meaning:

> Include the current version of this file in my next commit.

To stage all relevant changes:

``` bash
git add .
```

The process is:

``` text
Modified files
     |
     | git add
     v
Staging area
```

The staging area lets you decide exactly which changes belong in the
next saved version.

------------------------------------------------------------------------

## 5. `git commit` - Save a Version Locally

After staging your changes:

``` bash
git commit -m "Complete PSX data download notebook"
```

Meaning:

> Create a permanent local snapshot of the staged changes.

For example:

``` text
Work
 |
 v
git add
 |
 v
git commit
 |
 v
Version 1

More work
 |
 v
git add
 |
 v
git commit
 |
 v
Version 2
```

Because Git stores version history, you normally do not need filenames
such as:

``` text
analysis_final.ipynb
analysis_final2.ipynb
analysis_latest.ipynb
analysis_really_final.ipynb
```

Keep a clean filename and let Git maintain the versions.

------------------------------------------------------------------------

## 6. `git push` - Send Your Commits to GitHub

``` bash
git push
```

Meaning:

> Send my local commits to the remote GitHub repository.

Remember the distinction:

-   **`git commit`** saves a version in your local Git repository.
-   **`git push`** sends your committed versions to GitHub.

Conceptually:

``` text
YOUR COMPUTER                 GITHUB

Commit 1
Commit 2
Commit 3
    |
    | git push
    +-----------------------> Commit 1
                              Commit 2
                              Commit 3
```

------------------------------------------------------------------------

## 7. `git pull` - Get New Changes from GitHub

``` bash
git pull
```

Meaning:

> Download the latest changes from GitHub and integrate them into my
> local project.

This is useful when:

-   you edited a file directly on GitHub;
-   you worked on the repository from another computer;
-   another collaborator changed the repository.

A good habit is to run `git pull` before beginning a new work session.

------------------------------------------------------------------------

## 8. Normal Research Workflow

At the beginning of your work:

``` bash
cd D:\Research\Data-Analytics
git pull
```

Then work normally in Python, Jupyter, R, Stata-related files,
documentation, or other project files.

When you finish a meaningful piece of work:

``` bash
git status
```

Review the changes.

Then:

``` bash
git add .
```

Create a descriptive commit:

``` bash
git commit -m "Add daily stock return calculations"
```

Send it to GitHub:

``` bash
git push
```

The complete workflow is:

``` text
START
  |
  v
git pull
  |
  v
Work on project
  |
  v
git status
  |
  v
git add .
  |
  v
git commit -m "Describe the change"
  |
  v
git push
  |
  v
FINISHED
```

------------------------------------------------------------------------

## 9. `git log` - View Previous Commits

To see the project's version history:

``` bash
git log --oneline
```

Example:

``` text
a82c19f Add daily stock return calculations
73e621a Complete PSX data download notebook
51c79e2 Add initial project structure
```

Each line represents a saved version of the project.

------------------------------------------------------------------------

## 10. `git restore` - Discard Uncommitted Changes

If you changed a tracked file but want to discard those changes:

``` bash
git restore notebooks/psx_analysis.ipynb
```

**Warning:** this removes uncommitted changes from that file. Use it
carefully.

Before using `git restore`, it is good practice to run:

``` bash
git status
```

and make sure you really want to discard the changes.

------------------------------------------------------------------------

## 11. Six Essential Git Commands

  ---------------------------------------------------------------------------
  Command                     Meaning                 When to Use
  --------------------------- ----------------------- -----------------------
  `git clone URL`             Download the repository Usually once
                              for the first time      

  `git status`                Check what has changed  Frequently

  `git pull`                  Get the latest GitHub   Before starting work
                              changes                 

  `git add .`                 Stage your changes      After completing work

  `git commit -m "message"`   Save a version locally  After meaningful
                                                      changes

  `git push`                  Send commits to GitHub  After committing
  ---------------------------------------------------------------------------

------------------------------------------------------------------------

## 12. Quick Reference

### Start a work session

``` bash
cd D:\Research\Data-Analytics
git pull
git status
```

### Finish a work session

``` bash
git status
git add .
git commit -m "Describe what you changed"
git push
```

### Check that everything is synchronized

``` bash
git status
```

Ideally Git should report:

``` text
On branch main
Your branch is up to date with 'origin/main'.

nothing to commit, working tree clean
```

This means your local working directory has no uncommitted changes and
your branch is synchronized with the remote branch.

------------------------------------------------------------------------

## Core Rule to Remember

**Pull -\> Work -\> Status -\> Add -\> Commit -\> Push**

For most individual research projects, understanding this sequence is
enough to use Git effectively and safely.
