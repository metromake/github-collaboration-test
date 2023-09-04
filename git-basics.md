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

A collection of useful _.gitignore_ templates for different kind projects [in GitHub](https://github.com/github/gitignore).

---

## Git workflows (branching strategies)

- **Feature Branching:** In this strategy, each new feature or task gets its own branch. Developers work on these branches, and when the feature is complete, it's merged back into the main development branch.
  - Advantages: Isolates new features, makes it easy to track progress on individual features, and allows for concurrent development of multiple features.
  - Disadvantages: Can lead to a large number of branches, and merging can become complex if there are many long-lived feature branches.

- **Gitflow Workflow:**  Gitflow is a branching model that defines specific branch naming and usage conventions. It typically includes a "develop" branch for ongoing development, "feature" branches for new features, "release" branches for preparing releases, and a "master" branch for stable releases.
Advantages: Provides a structured and organized workflow, making it easier to manage releases and hotfixes.
  - Disadvantages: Can be seen as overcomplicated for smaller projects and may introduce unnecessary overhead.

- **GitHub Flow:**  GitHub Flow is a simplified workflow often used in open-source and web development. It involves a "master" branch for production-ready code and feature branches for development. Changes are continuously integrated into the master branch through pull requests.
  - Advantages Simple and effective for continuous deployment and collaboration. Suitable for fast-paced, web-centric projects.
  - Disadvantages: May not be suitable for projects with longer release cycles or complex version management.

- **GitLab Flow:** Similar to GitHub Flow, GitLab Flow focuses on a simple workflow using merge requests. It includes feature branches for development and long-lived "production" and "staging" branches for different stages of the development process.
  - Advantages Well-suited for teams using GitLab's built-in features. Provides clear separation of different development stages.
  - Disadvantages: May require some adaptation if not using GitLab's specific tools and features.

- **Centralized (aka Trunk-Based) Development:** In this strategy, there's only one long-lived branch (typically "main" or legacy "master"). All development work, including new features, bug fixes, and experiments, is done on this branch. Continuous integration practices ensure that the code on the main branch is always in a deployable state.
  - Advantages Simplicity, encourages small and frequent commits, and ensures a very stable "trunk" at all times.
  - Disadvantages: Can be challenging for larger teams or complex projects, as it requires strict discipline and automation.

- **Release Branching:** In this strategy, there's a "develop" branch for ongoing work, and when it's time for a release, a "release" branch is created. Bug fixes for the release are made on the release branch, and once it's stable, it's merged into "master."
  - Advantages Provides a way to stabilize the code for releases while still allowing ongoing development.
  - Disadvantages: Can introduce complexity in managing multiple branches, and merging can be challenging.

Reading

- [Comparing Git Workflows: What You Should Know](https://www.atlassian.com/git/tutorials/comparing-workflows) (Atlassian)

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

## Working with remote repositories

`git pull`, `git push`, and `git fetch` are essential Git commands for interacting with remote repositories. They allow you to synchronize your local repository with a remote repository, exchange changes with collaborators, and keep your codebase up to date.

Before testing these commands you need to create an empty project for example in Github and follow the instructions to set the remote in your local repo. Additionally, you need to [setup authentication with Github](https://docs.github.com/en/get-started/getting-started-with-git/caching-your-github-credentials-in-git).

### Git Pull

The `git pull` command is used to fetch changes from a remote repository and merge them into your current branch. It's a combination of `git fetch` and `git merge`.

```bash
# <remote> is the name of the remote repository (e.g., origin is the default remote name).
# <branch> is the branch from the remote repository that you want to pull and merge into your current branch.
git pull <remote> <branch>

# Example
git pull origin main
```

### Git Push

The `git push` command is used to send your local commits to a remote repository. It updates the remote repository with your changes.

## Command-line `git` vs. GUIs

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


[wiki2]: https://en.wikipedia.org/wiki/Git_(software)

Read: [What is version control?](https://www.atlassian.com/git/tutorials/what-is-version-control)

_VCS is a fundamental tool for software development, and it's used not only by individual developers but also by teams and organizations of all sizes to manage and collaborate on software projects efficiently. It plays a crucial role in ensuring code quality, collaboration, and project management in the software development process._

---

## Basic concepts

- **Repository** (or **Repo**): storage for all files, metadata and their revision data for a project
- **Commit**: revision of code (a snapshot of the repository at a specific point in time)
- **Branch**: parallel separate line of development within a repository
- **Tag**: special label for a revision (e.g. Release v. 1.1)
- **Clone**: taking a full copy of an existing repository
- **Checkout**: choosing specified version of code or development branch to work with
- **Merge**: combining changes of different branches together
- **Conflict**: occurs when there is different modifications in the same file while trying to merge branches

---

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

Tags are used to mark important points in the history of a project, such as software releases or significant milestones. Unlike branches, which can move as new commits are added, tags are static and provide a way to uniquely identify and reference specific commits.

Creating a tag:

```sh
git tag <tagname>  # Tag the current commit
git tag -a <tagname> -m "Tag message"   # Create an annotated tag with a message
git tag <tagname> <commit>   # Tag a specific commit
```

Listing & viewing tags:

```sh
git tag  # list all the tags in your repository
git show <tagname>  # view details about a specifig tag
```