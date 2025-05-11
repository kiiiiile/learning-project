# Introduction to Use

> This is a simple introduction to the use command(Using the git command).

## Install winget

- By the following url to install winget on your system.

[Install winget on your system](https://github.com/microsoft/winget-cli/releases)

## Install powershell

- By the following commend to install powershell on your system.

```cmd
winget install --id Microsoft.PowerShell --source winget
```

## Install git

- By the powershell install git on your system.

```powershell
winget install --id Git.Git --source winget
```
## How to use the git command in GitHub?

### Push the local project to GitHub.
1. Create and deploy SSH key on GitHub.

```powershell
# 1.Configure the user name and email address.
git config --global user.name "your name"
git config --global user.email "your email"

# 2.Create SSH key.
ssh-keygen -t rsa -C "your email"

# 3.Copy the public key to GitHub SSH key.
C:\Users\yourname\.ssh\id_rsa.pub

```

2. Create a new repository on GitHub.

3. Push the local project to GitHub.

```powershell
# 1.Initialize the local project.
git init

# 2.Add all files to the staging area.
git add .
# Or push some files to the staging area.
# 1).Create the .gitignore file in the current path.
# 2).Add files/folders that do not require remote management to the .gitignore file.
New-Item -Path ".\gitignore" -ItemType File -Force
git add .

# 3.Commit the changes.
git commit -m "first commit"

# 4.Add the remote repository.
git remote add origin "URL_ADDRESS"

# 5.Push the changes to the remote repository.
git push -u origin main
```

### Pull the remote project to local.

```powershell
# First, check the remote repository.
git remote -v

# Clone the remote project to current path.
git clone "URL_ADDRESS"
# Clone the remote project to other path.
git clone "URL_ADDRESS" "LOCAL_ATHER_PATH"

# When the wait is complete, look at the file.
cd "LOCAL_ATHER_PATH"
ls
git status # Check the status of the local project.
```
### Update the local project to remote.

```powershell
# 1.Check the status of the local project(red is not staged, green is staged).
git status

# 2.Pull the remote project to local.
git pull origin main

# 3.Add files to the staging area(conflict-free/Be in conflict).

# a.Conflict-free.
# 1).Add all files to the staging area.
git add.
# 2).Add some files to the staging area.
git add "FILE_NAME"

# b.Be in conflict.
# Resolving conflict files.
git add "FILE_NAME" # Add the conflict files to the staging area.
git commit -m "merge: Update the conflict files." # Commit the changes.

# 4.Commit the changes.
<# 
-m: commit message.
fix: fix bug.
feat: add new features/.
chore: update build tasks, package manager configs, etc.
refactor: refactor code.
test: add or modify tests.
style: format code.
perf: improve performance.
ci: update continuous integration.

build: update build system or dependency modify.
revert: undo the previous commit.
wip: work in progress(temporary commit).
 #>
# Example:
git commit -m "fix: Fix email validation failing when users register

Details:Modified the regular expression of the EmailValidator class,Email addresses with a plus sign can now be properly validated.

Closes #123"

# 5.Push the changes to the remote repository.
git push origin main
```

### Branch management.

```powershell
# 1.Check the branch.
git branch # Check the current branch.
git branch -a # Check all branches.
git branch -r # Check remote branches.
git branch -l # Check local branches.

# 2.Create a new branch.
git checkout -b "BRANCH_NAME" # Create a new branch and switch to it.
git checkout -b "BRANCH_NAME" "BASE_BRANCH_NAME" # Create a new branch based on the specified base branch and switch to it.

# 3.Switch to the specified branch.
git checkout "BRANCH_NAME" # Switch to the specified branch.
git switch "BRANCH_NAME" # Switch to the specified branch.

# 4.Delete the specified branch.
git branch -d "BRANCH_NAME" # Delete the specified branch.
git branch -D "BRANCH_NAME" # Force delete the specified branch.
git push origin --delete "BRANCH_NAME" # Delete the specified branch on the remote repository.

# 5.Modifying the branch name.
git branch -m "OLD_BRANCH_NAME" "NEW_BRANCH_NAME" # Modifying the branch name.
git push origin -u "NEW_BRANCH_NAME" # Push the branch to the remote repository.
git push origin --delete "OLD_BRANCH_NAME" # Delete the old branch on the remote repository.

# 6.Merge the specified branch to the current branch.
git merge "BRANCH_NAME" # Merge the specified branch to the current branch.
git merge --no-ff "BRANCH_NAME" # Force create merge commit.
git merge --abort # Abort the merge.
git merge --continue # Continue the merge.
```

### Reset and revert.

```powershell
# 1.Reset the specified branch to the specified commit.
git reset --hard "COMMIT_ID" # Reset the specified branch to the specified commit.
git reset --soft "COMMIT_ID" # Reset the specified branch to the specified commit, but keep the changes.

# 2.Revert the specified commit.
git revert "COMMIT_ID" # Revert the specified commit.
git revert --no-commit "COMMIT_ID" # Revert the specified commit, but keep the changes.
git revert --abort # Abort the revert.
git revert --continue # Continue the revert.
git push origin main # Push the changes to the remote repository.
```