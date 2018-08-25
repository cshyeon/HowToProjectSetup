# Project Setup
How to set up a pre-development project

# Preparation

### Editor
- vscode

### Environment
- node.js
- npm OR yarn   
- git (+ Github account)
  
# Setup

## 0. Make project folder
- Type the below code on terminal (in editor, cmd, powershell or bash)
```bash
mkdir foldername
cd foldername 
```
### Make essential folder and files in project folder
- folder: dist, src
- files: README.md
  
## 1. VCS (Version Control System)  
```bash
git init # Setup the git on project folder
git config user.email "your@email.com" # or git config --global user.email "your@email.com"
git config user.name "your name" # or git config --global user.name "your name"
```
- Create .gitignore file
- Then commit first setup files.

``` bash
git add -A
git commit -a -m "First project setup Commit"
```

- Make github repository at [Github](https://github.com)
```bash
git remote add origin 'your.github.repository.url' # Add remote repository
git push origin master  # Push the first commit to remote repository 
```

### Github SSH setting (optional)
- Create your SSH key set
```bash
cd ~ # your user account folder
ssh-keygen  # If your OS is windows, you can type the code in 'Git Bash' terminal.
# If 'ssh-keygen' command has been ran completely, two files are created in '~/.ssh'
# The 'id_rsa' file is private key, 'id_rsa.pub' file is public key
cat ~/.ssh/id_rsa.pub # Show public key's content
```

- You have to upload public key's content to your Github account setting
  + github login -> settings -> SSH and GPG keys -> New SSH key -> upload your public key's content(cat ~/.ssh/id_rsa.pub)

- Set git remote url
```bash
git remote set-url origin "your github repository SSH!'s url"
git remote show origin # Make sure fetch, push url has changed.
```

### Make git's dev branch
- 'master' branch will be used to stable code version.
- 'dev' branch will be used to development stage.
```bash
git branch dev    # Create dev branch
git checkout dev  # Move to dev branch
git push origin dev # Apply the dev branch to the remote repository.
```