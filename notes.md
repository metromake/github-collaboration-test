    1  git clone https://github.com/mattpe/git-intro.git
    2  cd git-intro
    3  git remote add origin https://github.com/metromake/git-intro.git
    4  git branch -M main
  jjahdkfad
  asda
  sda
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

  d
  sad
  agd
  sfgfd
  gfd

  sg
  r
  gr

  ---

### Resolving conflicts

1. ** changes in the other branch.
   - The `>>>>>>> branch-name` marker indicates the end of their changes.
   - Many editors and IDEs provide tools for doing this more easily
3. **Manually Resolve the Conflict**:
   - Edit the file to choose which changes to keep and how to combine them.
   - Remove conflict markers and any extra spacing or lines used for markers.
4. **Save the File**:
   - Save the file with your changes.
5. **Repeat as Needed**:
   - If there are conflicts in multiple files, repeat the conflict resolution process for each file.
6. **Add and Commit**:
   - After resolving all conflicts, add the files to the staging area using `git add <list of files or .>`.
   - Commit the changes using `git commit -m "commit message"`. Git will create a new merge commit.
7. **Test Your Changes**:
   - After resolving conflicts, it's important to test your code to ensure that the changes are correct and functional.

Remember that conflicts are a natural part of collaborative development. Good communication with your team is essential to coordinate changes and minimize conflicts. Additionally, using version control best practices, such as keeping branches up to date and using feature branches, can help reduce the frequency of conflicts.

---