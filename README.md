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

## 0. vscode setting
- Custom editor configuration  
Open the command palette window(shortcut 'F1') -> open user settings -> user settings
```javascript
{
    /* Prettier */
    "prettier.eslintIntegration": true,

    /* File */
    "files.eol": "\n",        // End of line 'LF'
    "editor.tabSize": 2,

    /* Editor */
    "editor.minimap.enabled": false,  
    "window.zoomLevel": 0,  

    "search.exclude": {
        "**/node_modules": true
    }, 
}
```

### extensions
- Install useful extension for develeopment.
- Required extension: `ESLint`, `Prettier`

## 0.1 Make project folder
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

## 2. NPM initialize
- Create package.json file 
```bash
npm init # To create package.json file
```

## 3. Lint (eslint)
- Setup eslint for code formatting
```bash
npm install --save-dev eslint eslint-config-airbnb-base eslint-plugin-import
```

- Create eslint configuration file `.eslintrc.js` in project's root folder
```javascript
module.exports = {
    "env": {
        "browser": true,
        "es6": true,
        "node": true
    },
    "parserOptions": {
        "sourceType": "module"
    },
    "extends": [
        "airbnb-base"
    ],
    "plugins": [        
        'import'
    ],
};
```

# Vue.js project setup
## 1. Use `vue-cli` webpack template
- Install `vue-cli`
```bash
npm install -g @vue/cli # For vue-cli 3.0
npm install -g @vue/cli-init # For vue-cli 2.0 !!Required in this setup
```

- Make `vue-cli` template
```bash
vue init webpack [foldername] # e.g) vue init webpack client
#...
#Vue build => standalone
#vue-router => yes
#Use Eslint => yes
#ESlint preset => Airbnb
#Unit tests => yes
#Pick test runner => karma + mocha
#e2e setup nightwatch => y
#Should we run `npm install` ... => npm OR type manually `npm install`
cd [foldername] # e.g) cd client
```

## 2. Install `sass` modules
- To use `sass`, install modules
```bash
npm install -D node-sass sass-loader
npm start
```
