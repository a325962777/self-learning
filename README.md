---
marp: true
theme: default
paginate: true
style: |
  section {
    background-color: rgba(191, 250, 250, 0.908);
    
  }
---


# Git Command :
#   pre-commit :


## description 
Pre-commit is a hook in Git, which is a powerful version control system widely used for tracking changes in source code during software development. A pre-commit hook is a script that runs automatically every time you try to make a commit in Git. Its primary function is to inspect and potentially reject changes that do not meet certain criteria before they are committed to the repository.


---


##  Use-Cases  
###  Basic Use-Case
  - **Code Formatting**: Automatically format code to follow style guidelines.
  - Example: Running `prettier` to format JavaScript code.


  ---


### Advanced Use-Cases
- **Linting**: Ensure code quality by running linters like ESLint for JavaScript or Pylint for Python.
- **Running Tests**: Execute unit tests to make sure new changes don't break existing functionality.
- **Security Checks**: Run security tools to detect vulnerabilities before committing.


---


## Pros and Cons
### Pros
- **Consistency**: Ensures code consistency and adherence to standards.
- **Quality Control**: Prevents commits that don't meet quality checks.
- **Automation**: Reduces manual checks by automating the validation process.


---


### Cons
- **Slower Commits**: Can slow down the commit process if the hooks run long tasks.
- **Complexity**: Managing and maintaining pre-commit hooks can add complexity to the development workflow.


---


## Coding Examples
### Setting Up a Pre-Commit Hook
 Create a file named `pre-commit` in the `.git/hooks` directory of your repository:

 
```sh
#!/bin/sh
# Run ESLint before committing
eslint .
if [ $? -ne 0 ]; then
  echo "ESLint failed. Commit aborted."
  exit 1
fi -->
```


---



## Alternatives
### Pre-commit Framework
A framework for the management and maintenance of hooks with many languages ​​in advance that allows you to manage the hooks in a version-controlled file.

### Example:
### 1. .pre-commit-config.yaml
Activating hooks in a convenient and orderly way using a YAMEL file that defines the desired hooks and rules.

repos:
- repo: https://github.com/pre-commit/pre-commit-hooks
  rev: v3.2.0
  hooks:
    - id: trailing-whitespace
    - id: end-of-file-fixer
### An actual example of running the hook in practice
![alt text](image.png)

### 2. Git Hooks Manager
Tools like Husky for JavaScript projects
Manage Git hooks with ease in projects using npm.

npm install husky --save-dev
npx husky install
npx husky add .husky/pre-commit "npm test"
### An actual example of running the hook in practice
![alt text](image-1.png)

 ---

 #   .gitignore :


## description 
.gitignore is a configuration file in Git that allows you to define which files and folders to ignore during versioning. The purpose of this file is to prevent tracking of files that should not be part of the repository and have no dependencies on them, such as local configuration files, temporary files, and binary folders. The file contains a list of patterns that define which files or folders to ignore.


---


##  Use-Cases  
###  Basic Use-Case
  - **Ignoring temporary files**: like `*.tmp` or `*.log`.
```plaintext
  *.tmp
  *.log
  ```
- **Ignoring local configuration files**: like `.env`,`config.yaml`


  ---


### Advanced Use-Cases
- **Ignoring working folders**: like `node_modules/` or `vendor/.`
- **Ignoring files created by certain tools**: like `.idea` or `.vscode`


---


## Pros and Cons
### Pros
- **Keeping the database clean**: Preventing contamination of the database with unnecessary files.
- **Automation**: Saves time by eliminating the need to add each file manually.
- **Simplicity and flexibility**: Easy to set up and use for all types of files.


---


### Cons
- **Regular maintenance is required**: The file must be updated over time according to changes in the project.
- **Limited capabilities**: Dynamic behavior based on conditions cannot be defined.


---


## Coding Examples
- **Ignoring temporary files and binaries**
   - *.tmp
   - *.log
   - *.exe
   - *.dll
- **Ignoring local configuration files**
   - .env
   - config.yaml
- **Ignoring work folders**
   - node_modules/
   - vendor/
-**Ignoring files in subfolders at any depth level**
   - **/debug.log


---



## Alternatives
 - **.git/info/exclude**: This file works like .gitignore, but only affects the local computer and is not stored in the repository.
 - **Configuration management tools**: Tools like EditorConfig that can help keep certain files out of the loop.
 - **Git hooks**: Pre-commit hooks can be used to ensure that unnecessary files do not enter the repository.
### Example:

### An actual example of actually running a gitignore file
![alt text](image-2.png)


 ---


 #   git remote :


## description 
git remote mainly refers to the possibility to manage and duplicate links to external code repositories in the git management system (Git). With the help of the "git remote" commands, you can add, remove, change and manage the links to these external code repositories. It allows development teams to collaborate, access code remotely, and manage the development process in an efficient and organized manner.


---


##  Use-Cases  
###  Basic Use-Case
  - **Cloning Repositories**: Use git remote to add a remote repository URL when cloning a repository.
  - Example: git clone <repository-url>



  ---


### Advanced Use-Cases
- **Collaboration**: Managing collaborative workflows by adding and managing multiple remotes for fetching, pushing, and pulling changes.
- **Forking**: Forking repositories on platforms like GitHub and setting up remotes to track upstream changes.
- **Deployment**: Deploying code to production or staging environments by pushing changes to remote servers.


---


## Pros and Cons
### Pros
- **Flexibility**: Enables working with multiple remote repositories simultaneously.
- **Collaboration**:  Facilitates team collaboration by allowing easy sharing and syncing of code.
- **Deployment**: Essential for deploying applications and managing different deployment environments.


---


### Cons
- **Complexity**: Managing multiple remotes can lead to confusion or errors if not handled carefully.
- **Dependency**: Relies on network connectivity and permissions for remote operations.


---


## Coding Examples
 - **Adding a Remote**
 ```sh
 git remote add origin <remote-url>
```
 - **Listing Remotes**
 ```sh
 git remote -v
```
 - **Renaming a Remote**
 ```sh
 git remote rename origin upstream
```

 
---



## Alternatives
 - **HTTPS vs. SSH URLs**
   Different ways to specify remote URLs based on authentication preferences (HTTPS for username/password, SSH for SSH keys).
 - **Git Submodules**
   For including one Git repository as a subdirectory of another Git repository, managing dependencies across repositories.
 - **Third-party Git Hosting Services**
   Utilizing platforms like GitLab, Bitbucket, or Azure DevOps for hosting Git repositories with integrated remote management features.


   ---



### Example:
   - **By running this command:**
       ![alt text](image-3.png)

       #### Redirect to this address - repository to git remote:
      file:///C:/Program%20Files/Git/mingw64/share/doc/git-doc/git-remote.html
   - **By running this command:**
       ![alt text](image-4.png)
     #### The result is the display of all the remotes linked to the pool:
       ![alt text](image-5.png)


 ---


#   git pull :


## description 
git pull is a Git command used to update the local repository with the latest changes from the remote repository. The command combines two operations: git fetch, which fetches the changes from the remote repository, and git merge, which merges these changes into the current local branch. The command is to ensure that your local code is up to date with the latest code found in the remote repository.


---


##  Use-Cases  
###  Basic Use-Case
  - **Updating Local Repository**: The primary use of git pull is to update the local repository with the latest chang
    - **Example**:  Running git pull origin main to fetch and mermain branch of the remote repository.


  ---


### Advanced Use-Cases
- **Automated Sync**: Integrating git pull in a CI/CD pipeline to ensure the latest code
- **Collaborative Development**: In a team environment, using git pull to frequently update the local repository with changes made
- **Rebasing Instead of Merging**:  Using git pull --rebase to rebas

---


## Pros and Cons
### Pros
- **Easy Updates**: Simplifi
- **Combines Fetch and Merge**: Combines the functionality of `git fgit fetch and git merge into a single command.
- **Streamlined Workflow**: Improves the efficiency of collaborative development by keeping local repositories u


---


### Cons
- **Automatic Merge Conflicts**: If there are conflicts between the local and remote changes, they need to be resolved manuall
- **Implicit Behavior**: The automatic merge behavior may sometimes lead to unexpected results if not used carefully.
- **Dependency on Network**: Requires a stable network connection to interact with the remote repository.


---


## Coding Examples
- **Pull latest changes from the remote repository's main branch**
```sh
   git pull origin main
   ```
- **Pull latest changes and rebase local commits on top of the remote changes**
```sh
   git pull --rebase origin main
   ```
- **Pull latest changes and handle conflicts if any**
```sh
git pull origin main
```
- **In case of conflicts, resolve them manually**
- **After resolving conflicts, complete the merge**
```sh
git add .
git commit -m "Resolved merge conflicts"
```


---



## Alternatives
 - **git fetch + git merge**: Fetches the latest changes from th
 ```sh
 git fetch origin
 git merge origin/main
```
 - **git rebase**: Reapplies local commits on top
 ```sh
 git fetch origin
 git rebase origin/main
```
 
 ---


### Example:

### An actual example of actually running a git pull commsnd
![alt text](image-6.png)


 ---


#   git push :


## description 
git push is a Git command used to push the contents of a local repository to a remote repository. It moves your commits from your local computer to a remote repository like GitHub, GitLab, or Bitbucket, so your changes are available to others.


---


##  Use-Cases  
###  Basic Use-Case
  - **Uploading Changes**: Afte
    - **Example**:  `git push origin main uploads` changes from the local main branch to the remote repository.


  ---


### Advanced Use-Cases
- **Pushing to a Specific Branch**: When working wi
  - **Example**: git push origin feature-branch pushes changesfeature-branch to the remote repository.
- **Force Pushing**: Overwrites the remote branch with your local branch. Use
  - **Example**: `git push --force origin main`
- **Pushing Tags**:  Uploads tags to the remote repository
  - **Example**: `git push origin v1.0.0`


---


## Pros and Cons
### Pros
- **Collaboration**: Allows multiple developers to work on the same project by sharing changes.
- **Backup**: Provides a remote backup of your code.
- **Continuous Integration**: Facilitates automated workflows and continuous integration by ensur


---


### Cons
- **Overwrite Risks**: Force pushing can overwrite other developers' changes.
- **Conflicts**: Pushing changes without pulling the latest changes from


---


## Coding Examples
- **Basic Push**: Pushes changes from your local main branch to the remote main branch.
```sh
   git push origin main
   ```
- **Force Push**: Forces the changes from your local main branch to overwrite the remote main branch
```sh
   git push --force origin main
   ```
- **Push a Specific Branch**: Pushes the feature-branch to the remote repository.
```sh
git push origin feature-branch
```
- **Push**: Pushes the tag v1.0.0 to t
```sh
git push origin v1.0.0
```


---



## Alternatives
 - **git pull**: Combines `git fetch` and `git merge` to update your local branch with chang
 - **git fetch**: Downloads objects a
 
 ---


### Example:

### An actual example of actually running a basic git push commsnd
![alt text](image-7.png)


 ---

