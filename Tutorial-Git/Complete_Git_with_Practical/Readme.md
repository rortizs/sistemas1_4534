## Complete Git Tutorial with Practical Exercises (3 Phases)

This tutorial covers Git commands in three phases: beginner, intermediate, and advanced. Each phase includes hands-on exercises to solidify your understanding.

**Phase 1: Beginner** (Essential commands for local version control)

This phase covers the fundamental commands for managing a local repository.

**1. Initialize a Repository:**

- **Command:** `git init`
- **Exercise:** Create a directory called `beginner_git_project`, navigate to it in your terminal, and run `git init`.
- **Solution:** ```bash
  mkdir beginner_git_project
  cd beginner_git_project
  git init

  ```

  ```

**2. Add Files to the Staging Area:**

- **Command:** `git add <file>` or `git add .`
- **Exercise:** Create the files `index.html` and `style.css` in the project directory. Add `index.html` to the staging area.
- **Solution:** ```bash
  touch index.html
  touch style.css
  git add index.html

  ```
  (To add both files: `git add .`)
  ```

**3. Check the Repository Status:**

- **Command:** `git status`
- **Exercise:** Check the current status of the repository.
- **Solution:** ```bash
  git status

  ```

  ```

**4. Make a Commit:**

- **Command:** `git commit -m "<message>"`
- **Exercise:** Commit the staged changes with the message "Initial commit".
- **Solution:** ```bash
  git commit -m "Initial commit"

  ```

  ```

**5. View Commit History:**

- **Command:** `git log`
- **Exercise:** View the commit history.
- **Solution:** ```bash
  git log

  ```

  ```

**6. Ignore Files:**

- **Command:** Create a `.gitignore` file and add patterns of files to ignore.
- **Exercise:** Create a `.gitignore` file and ignore all files with the `.log` extension.
- **Solution:** ```bash
  echo "\*.log" > .gitignore

  ```

  ```

**7. Modify Files and Make a Second Commit:**

- **Command:** `git add`, `git commit`
- **Exercise:** Modify `index.html`, add `style.css` to the staging area, and make a new commit with the message "Add styles and modify index".
- **Solution:**```bash

  # Edit index.html and style.css

  git add .
  git commit -m "Add styles and modify index"

  ```

  ```

**Phase 2: Intermediate** (Branching, merging, and remote work)

This phase covers branch management, merging changes, and interacting with remote repositories.

**1. Create a Branch:**

- **Command:** `git branch <branch_name>`
- **Exercise:** Create a branch named `develop`.
- **Solution:** ```bash
  git branch develop

  ```

  ```

**2. Switch Branches:**

- **Command:** `git checkout <branch_name>`
- **Exercise:** Switch to the `develop` branch.
- **Solution:** ```bash
  git checkout develop

  ```

  ```

**3. Make Changes and Commits on the Branch:**

- **Command:** `git add`, `git commit`
- **Exercise:** On the `develop` branch, modify `style.css` and commit the changes with the message "Style changes on develop branch".
- **Solution:** ```bash

  # Edit style.css

  git add style.css
  git commit -m "Style changes on develop branch"

  ```

  ```

**4. Merge the Branch into Master:**

- **Command:** `git merge <branch_name>`
- **Exercise:** Merge the changes from the `develop` branch into the `master` branch.
- **Solution:** ```bash
  git checkout master
  git merge develop

  ```

  ```

**5. Clone a Remote Repository:**

- **Command:** `git clone <url>`
- **Exercise:** Clone the repository `https://github.com/mojombo/grit` to a local directory.
- **Solution:** ```bash
  git clone <https://github.com/mojombo/grit>

  ```

  ```

**6. Configure a Remote:**

- **Command:** `git remote add <name> <url>`
- **Exercise:** Configure a remote named `origin` pointing to `https://github.com/mojombo/grit`.
- **Solution:** ```bash
  cd grit
  git remote add origin <https://github.com/mojombo/grit>

  ```

  ```

**7. Push Changes to a Remote:**

- **Command:** `git push <remote> <branch>`
- **Exercise:** (Requires your own repository on GitHub) Push the `master` branch to the `origin` remote.
- **Solution:** ```bash
  git push -u origin master

  ```

  ```

**8. Pull Changes from a Remote:**

- **Command:** `git pull <remote> <branch>`
- **Exercise:** Pull and merge changes from the `master` branch of the `origin` remote.
- **Solution:** ```bash
  git pull origin master

  ```

  ```

**9. Stashing:**

- **Command:** `git stash`, `git stash apply`
- **Exercise:** Make some changes to `index.html` without committing. Stash these changes. Then, switch to the `master` branch and apply the stashed changes.
- **Solution:** ```bash

  # Edit index.html

  git stash
  git checkout master
  git stash apply

  ```

  ```

**Phase 3: Advanced** (Rewriting history, submodules, conflict resolution)

**1. Interactive Rebase:**

- **Command:** `git rebase -i HEAD~<n>` (where `<n>` is the number of commits to rebase)
- **Exercise:** Rewrite the last 3 commits on your `master` branch, changing the message of the second commit.
- **Solution:** ```bash
  git rebase -i HEAD~3

  ```
  (Then, in the editor, change 'pick' to 'reword' on the line for the second commit, save and close the editor. Git will open another editor to change the commit message.)
  ```

**2. Cherry-pick:**

- **Command:** `git cherry-pick <SHA-1>`
- **Exercise:** On the `master` branch, pick a specific commit from the `develop` branch (using its SHA-1) and apply it to `master`.
- **Solution:** ```bash
  git checkout develop
  git log # Find the SHA-1 you want
  git checkout master
  git cherry-pick <SHA-1>

  ```

  ```

**3. Reflog:**

- **Command:** `git reflog`
- **Exercise:** View the reflog to see the history of HEAD movements.
- **Solution:** ```bash
  git reflog

  ```

  ```

**4. Reset --hard (use with caution):**

- **Command:** `git reset --hard <SHA-1>`
- **Exercise:** Undo the last 2 commits on the `master` branch using `reset --hard`.
- **Solution:** ```bash
  git reflog # Find the SHA-1 you want to go back to
  git reset --hard <SHA-1>

  ```
  **WARNING:** `reset --hard` deletes commits and changes. Use with extreme caution!
  ```

**5. Add a Submodule:**

- **Command:** `git submodule add <url> <path>`
- **Exercise:** Add the repository `https://github.com/libgit2/libgit2` as a submodule in the `libgit2` folder.
- **Solution:** ```bash
  git submodule add <https://github.com/libgit2/libgit2> libgit2

  ```

  ```

**6. Update a Submodule:**

- **Command:** `git submodule update --remote`
- **Exercise:** Update the `libgit2` submodule with changes from the remote repository.
- **Solution:** ```bash
  git submodule update --remote libgit2

  ```

  ```

**7. Resolve Merge Conflicts:**

- **Solution:** ```bash

  # create a conflict (edit the same file on both branches)

  git merge <branch_name> # merge the branches, causing a conflict

  # edit the conflicting file, remove conflict markers, and save

  git add <conflicted_file>
  git commit -m "Resolved merge conflict"

  ```

  ```
