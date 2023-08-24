# Git Exercises

## Exercise 0: Learn Git basics online courses (optional)

Some free online courses/tutorials available:

- [Git Started with GitHub](https://www.udemy.com/course/git-started-with-github/)
  - Learn the basics of Git and GitHub, with step-by-step instructions
- [Version Control with Git](https://www.coursera.org/learn/version-control-with-git) by Atlassian
  - Command line and Sourcetree GUI in use, Teacher's recommendation: **choose command line**
- [The Ultimate GIT 5-day Challenge](https://www.udemy.com/course/the-ultimate-git-5-day-challenge/)

(You need to create a free account to access the courses)

---

## Exercise 1: Git command line basics

1. Install Git if missing command line tools, [instructions](https://git-scm.com/book/en/v2/Getting-Started-Installing-Git).
2. Create a local repo by **cloning** (`git clone`) this lecture material from Github: <https://github.com/mattpe/git-intro.git>
3. Create a remote repository at Github
4. Change the remote _origin_ to point to your Github repo (tip: `git remote help`)
   - set new uri for _origin_, or:
   - remove existing _origin_
   - add new _origin_: url to your Github repo
5. Push the files to your Github repo
6. Create a file `notes.md` in your local repo and record all git commands you have used into that file (check command: `history`)
7. Add the file to the local git repo
8. Commit your changes (remember to write a comment)
9. Push changes to remote repo
10. Update the file by adding new commands to list and _add, commit & push_ changes again

---

## Exercise 2: Collaboration & solving conflicts

1. Form a team of ~3 members
2. Choose a Github repo (from ex. 1) of one of the team members and add write/push permissions to other members of the team (add collaborators in Github, every team member should be able to push to that repo)
3. all team members should clone the same remote repo
4. do individually at the same time as your team mates:
   - pull changes from remote repo (not needed if repo was cloned just before)
   - create and checkout a new development branch for your modifications  
   - edit files locally (e.g. add, remove & modify rows)
   - add & commit changes
   - merge your development branch to `master` branch
   - try pushing `master` to remote repo
   - resolve conflicts when needed, ([help](https://help.github.com/articles/resolving-a-merge-conflict-from-the-command-line/)), commit and push
5. Go back to 4 (once at least)

---

## Exercise 3: Git Workflow for the project

This is a group assignment. Design a branching strategy for your software development project.

Write a one page report describing the best git workflow for your team. Explain the reasons why you chose such a strategy. This document is a mutual agreement for your team how your code development flow should go. Descibe also what are the general guidelines for your commit messages.

Remember that the best branching strategy for your project depends on factors like team size, project size, release cadence, and development style. It's also important to document and communicate your chosen strategy to ensure that everyone on the team understands how to use it effectively.

---

### Returning exercises

Check related assignment in Oma for instructions.

---
