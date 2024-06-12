# Git Commands:
## Git Configuration:
```bash
git config --global user.name "Name"
git config --global user.email "mail"
git config --list
```

  - This two first commands set the global user name and the mail for Git.
  - When you commit changes to a Git repository, Git uses the user name and email address to identify the author of the changes. By setting these values globally, you ensure that your commits will be attributed to you across all your Git repositories.
  - the 3rd to show this configuration.
##  Git Manual:
```bash
git help
```
- `git help` is a command that provides access to Git's built-in help system. It displays a list of available Git commands, along with a brief description of each command.
## Git Status:
```bash
git status
```
- `git status` is a command that provides an overview of the current state of your Git repository. It displays information about the files and directories in your repository, including:

1. **Unstaged changes**: Files that have been modified but not yet added to the staging area (index).
2. **Staged changes**: Files that have been added to the staging area but not yet committed.
3. **Untracked files**: Files that are not being tracked by Git, but are present in your repository.
## Git add files to version control:
```bash
git add filename.ext
git add .
```
- `git add .` is a command that stages all changes in your current directory and subdirectories, including:

1. **New files**: Adds new files to the staging area.
2. **Modified files**: Stages changes to existing files.
3. **Deleted files**: Stages deletions of files.

## Git commit changes:
```bash
 git commit -m "message as title to the commit"
```
- `git commit` is a command that saves your changes to the local repository, creating a new snapshot of your project's history. The `-m` option allows you to specify a commit message, which is a brief description of the changes you've made.

## Git change tracking:
```bash
git diff
git log
```
- `git diff` compares the current state of your files with the last committed version, showing you the changes you've made since the last commit. This command is useful for:

1. **Reviewing changes**: Before committing, use `git diff` to review the changes you've made.
2. **Identifying mistakes**: Catch accidental changes or errors before committing.

- `git log` displays a list of commits, including the commit hash, author, date, and commit message. This command is useful for:

1. **Tracking changes**: View the history of changes to your project.
2. **Identifying commits**: Find specific commits by searching for keywords or commit hashes.

## Git updating head commit:
```bash
git commit --amend -m "Update my message !"
```
- This command updates the most recent commit with new changes and a new commit message.
- `git commit --amend` is a command that updates the most recent commit, allowing you to modify the commit message, add new changes, or both. This command is useful when you want to:

1. **Correct a mistake**: Update a commit message or add a file that was forgotten in the previous commit.
2. **Refine a commit**: Make minor changes to a commit, such as updating a file or adding a new change.

## Git revert:

```bash
git revert HEAD #return one step in the past commits
git revert HEAD~2 #return two steps in the past commits
git revert #return to the initial state  
```
- This command reverts a previous commit, undoing the changes it introduced.
- `git revert` is a command that creates a new commit that reverses the changes made in a previous commit. This command is useful when you want to:

1. **Undo a commit**: Revert a previous commit that introduced unwanted changes.
2. **Fix a mistake**: Correct a mistake made in a previous commit.

## Git ignore files:

- `.gitignore` file is used to specify the files that won't be included in version control
- files that won't be considered by Git.
- Example:
```.gitignore
key.txt
secret-files.txt
env-var
```
## Git branch management:

**Creating and Managing Branches**

1. `git branch <branch-name>`: Creates a new branch with the specified name.
2. `git branch`: Lists all local branches.
3. `git branch -a`: Lists all local and remote branches.
4. `git checkout -b <branch-name>`: Creates a new branch and switches to it.

**Switching Between Branches**

1. `git checkout <branch-name>`: Switches to the specified branch.
2. `git checkout -`: Switches to the previous branch.

**Merging Branches**

1. `git merge <branch-name>`: Merges the specified branch into the current branch.
2. `git merge --no-commit <branch-name>`: Merges the specified branch into the current branch, but does not commit the merge.
3. `git merge --abort`: Aborts a merge operation.

**Deleting Branches**

1. `git branch -d <branch-name>`: Deletes a local branch.
2. `git push origin --delete <branch-name>`: Deletes a remote branch.

**Renaming Branches**

1. `git branch -m <old-branch-name> <new-branch-name>`: Renames a local branch.

**Pushing and Pulling Branches**

1. `git push origin <branch-name>`: Pushes a local branch to a remote repository.
2. `git pull origin <branch-name>`: Pulls a remote branch into a local repository.

**Remote Branch Management**

1. `git remote add <name> <url>`: Adds a remote repository.
2. `git remote remove <name>`: Removes a remote repository.
3. `git remote rename <old-name> <new-name>`: Renames a remote repository.

**Other Branch Management Commands**

1. `gitk --all`: Displays a graphical representation of the commit history, including all branches.
2. `git log --graph --all`: Displays a text-based representation of the commit history, including all branches.
3. `git branch --set-upstream-to=<remote-branch>`: Sets the upstream tracking information for a local branch.

## Git conflict management:

Here's an overview of common Git commands used in conflict management:

**Conflict Detection and Resolution**

1. `git status`: Displays the status of the repository, including any conflicts.
2. `git diff`: Displays the differences between the current version and the previous version of a file, highlighting conflicts.
3. `git diff --staged`: Displays the differences between the staged and unstaged changes.

**Conflict Resolution**

1. `git add <file-name>`: Stages a file, resolving conflicts.
2. `git add -p <file-name>`: Interactively stages a file, allowing you to resolve conflicts.
3. `git checkout --ours <file-name>`: Checks out the "ours" version of a file, resolving conflicts in favor of the current branch.
4. `git checkout --theirs <file-name>`: Checks out the "theirs" version of a file, resolving conflicts in favor of the other branch.
5. `git merge --abort`: Aborts a merge operation, restoring the repository to its pre-merge state.

**Conflict Markers**

1. `git config --global merge.conflictstyle merge`: Sets the conflict style to "merge", which uses conflict markers (e.g., `<<<<<<<`, `=======`, `>>>>>>>`).
2. `git config --global merge.conflictstyle diff3`: Sets the conflict style to "diff3", which uses a three-way merge marker (e.g., `|||||||`).

**Merging and Rebasing**

1. `git merge --no-commit <branch-name>`: Merges a branch, but does not commit the merge, allowing you to resolve conflicts.
2. `git rebase <branch-name>`: Rebases a branch, replaying commits on top of the target branch, which can help resolve conflicts.
3. `git rebase --abort`: Aborts a rebase operation, restoring the repository to its pre-rebase state.

**Committing Conflict Resolutions**

1. `git commit -m "Resolved conflicts"`: Commits the conflict resolution with a meaningful commit message.
2. `git commit -a`: Commits all changes, including conflict resolutions.

**Other Conflict Management Commands**

1. `git ls-files -u`: Displays unmerged files, highlighting conflicts.
2. `git merge --no-ff <branch-name>`: Merges a branch, always creating a merge commit, even if the merge could be fast-forwarded.
3. `git reset --merge`: Resets the repository to its pre-merge state, discarding conflict resolutions.

## Git remote branch management:

**Pushing to a Remote Repository**

1. `git push origin <branch-name>`: Pushes the specified local branch to the remote repository's branch of the same name.
2. `git push origin <local-branch-name>:<remote-branch-name>`: Pushes the specified local branch to a differently named remote branch.
3. `git push origin HEAD`: Pushes the current branch to the remote repository, using the current branch name.

**Forcing a Push**

1. `git push origin +<branch-name>`: Forces a push, overwriting any changes on the remote branch.
2. `git push origin +<local-branch-name>:<remote-branch-name>`: Forces a push, overwriting any changes on the remote branch, even if it's not the same name.

**Deleting a Remote Branch**

1. `git push origin --delete <branch-name>`: Deletes a remote branch.
2. `git push origin :<branch-name>`: Deletes a remote branch (alternative syntax).

**Renaming a Remote Branch**

1. `git push origin <old-branch-name>:<new-branch-name>`: Renames a remote branch.

**Pushing Tags**

1. `git push origin --tags`: Pushes all tags to the remote repository.
2. `git push origin <tag-name>`: Pushes a specific tag to the remote repository.

**Pushing to a Non-Default Branch**

1. `git push origin <local-branch-name>:refs/heads/<remote-branch-name>`: Pushes a local branch to a non-default remote branch.

**Specifying the Remote Repository**

1. `git push <remote-name> <branch-name>`: Specifies a different remote repository to push to.

**Pushing with Options**

1. `git push --force-with-lease`: Forces a push, but only if the remote branch has not changed since the last fetch.
2. `git push --atomic`: Pushes multiple refs (e.g., branches, tags) atomically, ensuring either all or none are updated.
3. `git push --verbose`: Displays more detailed output during the push operation.

**Common Options**

1. `-u` or `--set-upstream`: Sets the upstream tracking information for a local branch.
2. `--dry-run`: Simulates a push, displaying what would happen without actually pushing.
3. `--no-verify`: Disables pre-push hooks.

**Pulling from a Remote Repository**

1. `git pull origin <branch-name>`: Pulls the specified remote branch into the local repository.
2. `git pull origin <remote-branch-name>:<local-branch-name>`: Pulls a remote branch into a differently named local branch.
3. `git pull origin HEAD`: Pulls the current branch from the remote repository, using the current branch name.

**Fetching from a Remote Repository**

1. `git fetch origin <branch-name>`: Fetches the specified remote branch, but does not merge.
2. `git fetch origin <remote-branch-name>:<local-branch-name>`: Fetches a remote branch into a differently named local branch.
3. `git fetch origin HEAD`: Fetches the current branch from the remote repository, using the current branch name.

**Managing Remote Repositories**

1. `git remote add <name> <url>`: Adds a new remote repository.
2. `git remote remove <name>`: Removes a remote repository.
3. `git remote rename <old-name> <new-name>`: Renames a remote repository.
4. `git remote set-url <name> <url>`: Updates the URL of a remote repository.
5. `git remote show <name>`: Displays information about a remote repository.