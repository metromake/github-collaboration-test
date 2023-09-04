hgadgfhahsdjksada
fas
fs
gdf
hderh
drgksfkjskfsd
fsjd
adkgdasgjksdhgklsgl
sdgjdg
kjwekgjwoigvjewiogjw
---

## Why to use VCS

_(Version Control System, revision control)_

- Compulsory tool for professional software development
- Track and trace code changes
- What is changed since last version and before?
  - Why, comments
  - When did that happen?
  - Who did that?
- Share project code (and development history) —> Collaboration
- Project backup?
- Example: [check revisions][wiki1] of an [Wikipedia article][wiki2]

[wiki1]: https://en.wikipedia.org/w/index.php?title=Git_(software)&action=history
## Git ignore

Which files and changes should be tracked with version control?

For example in following Eclipse Java project

![gitignore](images/gitignore.png)

only `src/` folder contains code files created by developers and everything else is generated automatically by Eclipse IDE (Integrated Development Environment) **->** `.gitignore` file for the project should be something like:

```txt
bin/
.settings/
.project
.classpath
```

`.git/` folder (contains the revision history etc.) and `.gitignore` file itself should be included in version control.

### Stuff to include

- all source code
- `README.md` and other documentation
- license
- `package.json` and other settings files
- `.gitignore` file: list of local files not to be included in the version control ->

### Stuff to exclude

- build targets and other automatically generated files
- packages managed e.g. by _npm_ (= _node_modules_ folder)
- any temp & OS specific files, like Apple's `.DS_Store`
- IDE/editor specific project files & folders

### Examples


---

### Merging changes

Merging is the process of combining changes from one branch into another. This is typically done when a feature or bug fix is complete and needs to be incorporated into another development branch or into the `main` branch.

1. Merge changes in another branch into the current branch: `git merge <OTHER-BRANCH>`.
2. If the branch you're merging into has not diverged from the source branch, Git performs a fast-forward merge. In this case, no actual merge commit is created; the branch pointer simply moves forward to the latest commit on the source branch. (No need to create commit manually.)
3. If there are changes in both the source and target branches that cannot be resolved automatically (i.e., there are conflicting changes to the same lines of code), Git performs a three-way merge. It creates a merge commit that represents the combination of the changes from both branches. You may need to [resolve any conflicts](#resolving-conflicts) manually before finalizing the merge.
4. If you encounter issues during a merge and want to abort the merge process, you can use: `git merge --abort`
5. Finally, after resolving conflicts and completing the merge, you need to commit the merge changes to finalize the process: `git commit -m "Merge branch 'source-branch' into 'target-branch'"`

#### Using `git rebase` to integrate changes

git rebase is a Git command used for modifying the commit history of a branch. Unlike git merge, which integrates changes from one branch into another with a new merge commit, git rebase rewrites the commit history by moving or combining commits from one branch onto another. This can result in a linear, more streamlined commit history.

Note that rebasing rewrites commit history, which can make it a powerful tool for maintaining a clean and linear history. However, it should be used with caution, especially in shared branches, because it can cause confusion and conflicts for other team members if they are also working on the same branch.

Read: [Merging vs. Rebasing](https://www.atlassian.com/git/tutorials/merging-vs-rebasing) (by Atlassian)



## `.git/`

- Contains everything else than the working copy of files
- "physical location" of the local git repo on the file system
- removing the folder deletes the repository completely, only files in current branch are saved

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
## [GitHub](https://github.com)

- **GitHub != Git** (Git is the application, GitHub is a company/service utilizing Git and providing a lot more than just version tracking.)
- Commercial service providing a remote git repository server, project management tools, wiki, issue tracker, webpage hosting, etc.
- has a wide user community
- **Fork**: Create a new Github project, clone the git repository of an existing project and add repo to the new project
- Almost _de facto_ hosting service for Open Source projects
- Repositories (projects) are public by default, private repos are accessible only for invited collaborators

## Other remote repository service providers

- [Bitbucket](https://bitbucket.org) is another popular git repo hosting service providing free private repos for small teams
- [GitLab](https://about.gitlab.com/install/) provides a commercial service or free open source community edition to installed on one's own server


- command-line version is the original with complete functionality
- most IDEs have built-in or plugin based integrations for common operations
- OS specific & cross-platform Git clients/apps
  - QGit
  - Gitg
  - Git Force
  - Sourcetree
  - GitHub Desktop
  - TortoiseGit
  - GitUp
  - Fork
  - GitFinder
  - GitKraken
  - SmartGit
  - Git Cola
  - GitFiend
  - Gittyup

_If you master the command-line it's easy to understand how git works and use diffenrent GUIs too._ Additionally, all new features are implemented first in original cli application.

## More learning materials

- Free book: [Pro Git](http://git-scm.com/book/en/v2)
- Basics at Codecademy: [Learn Git](https://www.codecademy.com/learn/learn-git)
- [GitHub Guides](https://guides.github.com/)
- [Atlassian Git Tutorials](https://www.atlassian.com/git/tutorials/)

---

- [The best Git branching strategies](https://blog.mergify.com/the-best-git-branching-strategies/) (by Hugo Escafit)

---

djagdjfjdkafkasbfbajbcsab c
sacanskjvnak

- **Repository** (or **Repo**): storage for all files, metadata and their revision data for a project
- **Commit**: revision of code (a snapshot of the repository at a specific point in time)
- **Branch**: parallel separate line of development within a repository
- **Tag**: special label for a revision (e.g. Release v. 1.1)
- **Clone**: taking a full copy of an existing repository
- **Checkout**: choosing specified version of code or development branch to work with
- **Merge**: combining changes of different branches together
- **Conflict**: occurs when there is different modifications in the same file while trying to merge branches

---
## Exercise 0: Learn Command line and Git basics online materials (optional)

Read: [Command Line for Beginners – How to Use the Terminal Like a Pro [Full Handbook]](https://www.freecodecamp.org/news/command-line-for-beginners/)

Some free online Git courses/tutorials available:

- [Git Started with GitHub](https://www.udemy.com/course/git-started-with-github/)
  - Learn the basics of Git and GitHub, with step-by-step instructions
- [Version Control with Git](https://www.coursera.org/learn/version-control-with-git) by Atlassian
  - Command line and Sourcetree GUI in use, Teacher's recommendation: **choose command line**
- [The Ultimate GIT 5-day Challenge](https://www.udemy.com/course/the-ultimate-git-5-day-challenge/)

## Git

- Development started By Linus Torvalds 2005
- Created initially for Linux kernel development
- The Stupid Content Tracker
- Distributed Version Control System (DVCS)
- Content agnostic: can be used for anykind of files
  - with some restrictions
  - full functionality for plain text files
- Is used locally (remote server not mandatory)

![arch image](images/git-arch.png)

### Synchronising with remotes

- `git clone <URI>`: clone an existing repository (create a new local copy of the repo)
- `git remote`: manage linking with remote repositories
- `git push`: upload the changes in local repo (new commits) to chosen remote repository
- `git pull`: download the changes in remote repo ( get new changes and commits) from remote repo
- `git fetch`: retrieves changes from a remote repository, but it does not automatically merge those changes into your local working branch

---

### Getting started and creating revisions

- Git stores snapshots of all edited files in commits

![Revisions illustration](images/git-revisions.png)

[Source](http://git-scm.com/book/en/v2/Getting-Started-Git-Basics)

1. Open terminal/Git bash in your local project folder
1. make sure you have set username and email for Git (these are saved within commit data)

    ```sh
    git config --global user.name "My Name"
    git config --global user.email my.email@example.com
    ```

1. Initialize git repo: `git init`
1. choose files with `git add`
1. commit chosen files with `git commit -m "my commit message"`
   - use describing commit messages, check: [How to Write Better Git Commit Messages – A Step-By-Step Guide](https://www.freecodecamp.org/news/how-to-write-better-git-commit-messages/)
   - previous commit can be replaced with: `git commit --amend -m "my commit message"`, Note that this modifies commit history and should not be used in published branches
   - before commits make sure that you are in the correct branch and have chosen correct files! (`git status`)

---

### Branching

- a branch is a separate line of development within a Git repository
- allows multiple developers to work on different features or fixes simultaneously without interfering with each other
- basically branches are just pointers to commits

---

### Tagging
