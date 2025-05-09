# Introduction to Use

> This is a simple introduction to the use command(Using the git command).

## install winget

- By the following url to install winget on your system.

[Install winget on your system](https://github.com/microsoft/winget-cli/releases)

## install powershell

- By the following commend to install powershell on your system.

```cmd
winget install --id Microsoft.PowerShell --source winget
```

## install git

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
```