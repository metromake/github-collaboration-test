    1  git clone https://github.com/mattpe/git-intro.git
    2  cd git-intro
    3  git remote add origin https://github.com/metromake/git-intro.git
    4  git branch -M main
  jjahdkfad
  asda
  sda
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

1. **Identify Conflicts**:
   When you attempt to merge or rebase a branch with conflicting changes, Git will notify you of the conflict in the terminal.
2. **Open the Conflicted File**:
   - Open the conflicted file in a code editor.
   - Git will mark the conflicting sections like this:

     ```plaintext
     <<<<<<< HEAD
     // Your changes
     =======
     // Their changes
     >>>>>>> branch-name
     ```

   - The `<<<<<<< HEAD` marker indicates the start of your changes.
   - The `=======` marker separates your changes from the changes in the other branch.
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