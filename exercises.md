# Git Exercises


---

## Git installation

- Command line user interface running in operating system's terminal is the original/default tool
  - Windows: [Git for windows](https://gitforwindows.org/) provides command line tools (git bash) and Graphic UI tools/integration to Windows explorer
  - MacOS: [Several options](https://git-scm.com/download/mac)
  - Linux/Unix: via package manager, e.g. `apt install git` or `yum install git`
- Multiple [graphical UIs](https://git-scm.com/downloads/guis) are available too  
- Integrated Git support or a plugin is provided for most/all popular IDEs

---

## Git basic usage & commands

### Local Git workflow

- `git init`: create a new git repository
- `git status`: check current status of the repo, **TIP:** Use this all the time to double-check what you are doing with your repo
- `git add [filenames]`: choose files for the next commit (add to staging area)
- `git commit`: save a version of chosen files (needs a message too, e.g. `-m "added new file"`)
- `git log`: show revision history
- `git branch <newBranchName>`: create a new branch based on the current branch
- `git tag`: create a reference to a specific commit in the repository's history
- `git checkout <branchName>`: choose a branch or a revision to work with
- `git diff`: shows the differences in files between working copy and the last commit
- `git merge`: combine changes from one branch into another
- `git rebase`: modify the commit history of a branch
- `git reset`: manipulate the state of the current branch by moving the branch pointer to a different commit (used e.g. to undo changes, unstage files, etc.)
- `git stash`: temporarily save changes that you've made in your working directory but do not want to commit at the moment
- `git reflog`: "reference log", maintains a log of all reference updates in a Git repository including branch creations, checkouts, commits, merges, rebases, etc.
- `gitk`: graphical user interface (GUI) tool that comes bundled with Git

![Workflow graph](images/git-workflow.png)

[Source](http://git-scm.com/book/en/v2/Getting-Started-Git-Basics)

## Exercise 3: Git Workflow for the project

This is a group assignment. Design a branching strategy for your software development project.

Write a one page report describing the best git workflow for your team. Explain the reasons why you chose such a strategy. This document is a mutual agreement for your team how your code development flow should go. Descibe also what are the general guidelines for your commit messages.

Remember that the best branching strategy for your project depends on factors like team size, project size, release cadence, and development style. It's also important to document and communicate your chosen strategy to ensure that everyone on the team understands how to use it effectively.

---

### Returning exercises

Check related assignment in Oma for instructions.



(You need to create a free account to access the courses)

---



---

---
