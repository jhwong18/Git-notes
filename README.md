## Table of Contents

[Git Objects, Git IDs](#Git-object-Git-IDs)

  1. [Repository](#repository)
  2. [Working Directory](#working-directory)

[File Status Lifecycle](#file-status-lifecycle)

[Git Configuration](#git-configuration)

  1. [Configuration Architecture](#configuration-architecture)
  2. [Configuration Levels](#configuration-levels)
  3. [Ignoring some files and folders by default](#ignoring-some-files-and-folders-by-default)

[Branch](#branch)

[Git Commands](#Git-commands)

  1. [How to read Git commands](#How-to-read-Git-commands)
  1. [Git configurations](#Git-configurations)
  2. [Create Repository](#Create-Repository)
  3. [Add, Commit and Push to Remote Repository](#Add-Commit-Push-Repository)
  3. [Git Status](#Git-Status)
  3. [Git Tags](#Git-Tags)
  3. [Creating a file on Git Bash](#Create-file-on-Git-Bash)
  3. [Git Merge](#Git-Merge)
  3. [Working Directory](#working-directory)



[References](#references)

<br />

## Git Objects, Git IDs
<a name="Git-object-Git-IDs"></a>
Git objects, Git IDs
Internally, Git uses objects to store four types of things. A commit object is a simple text file that contains information such as the commit user information, commit message, a reference to the commits parent or parents and a reference to the root tree of the project. That information is all that Git needs to rebuild the full contents of a commit. An annotated tag is a reference to a specific commit. A tree is an object that contains a list of the file names and directories inside of a directory. A blob is an object that stores the content of a file that is being managed by Git. A typical Git user may only interact with commit objects and tags, letting Git worry about the details related to trees and blobs. Git keeps these objects internally in something called the object store but you typically don't directly interact with the object store.

 
 - Getting Git IDs (SHA-1) on Git Bash
   ```bash
   git hash-object <file>
   ```
 - OR operation


## Repository and Working Directory

## Git Commands

<a name="How-to-read-Git-commands"></a>
How to read Git commands
 
 - Change the command's behavior
   ```bash
   -f or --flag
   ```
 - OR operation
   ```bash
   |
   ```   
 - Optional
   ```bash
   [optional]
   ```
 - placeholder (required, not optional)
   ```bash
   <placeholder>
   ```   
 - placeholder (optional)
   ```bash
   [<placeholder>]
   ```   
   
 - Grouping
   ```bash
   ()
   ```   
 - Disambiguates the command (separates subcommand arguments)
   ```bash
   --
   ```   
<a name="#Git-configurations"></a>
Git Configurations

 - Configure user information, --system flag applies to all users, --global flag applies to all repos in a user, --local applies to only current repos

   ```bash
   git config user.name
   git config user.email
   git config --global user.name
   git config --global user.email
   git config --system user.name
   git config --system user.email
   git config --local user.name
   git config --local user.email
   ```
   
   
 - Enables helpful colorization of command line output
   ```bash
   git config --global color.ui auto
   ```   

 - Specify the type of editor to use
 ```bash
   git config --global core.editor nano
   ```   


<a name="#Create-Repository"></a>
Create Repository

 - Turn an existing directory into a local git repository
 ```bash
   git init
   ```   

 - Clone (download) a local repository from a remote repository that already exists on GitHub, including all of the files, branches, and commits
   ```bash
   git clone <url> [project name]
   ```

 - Create a local repository and push a to a remote repository that already exists on GitHub with new commits
   ```bash
   git clone [url]
   git add <file>
   git commit -m "message"
   git push origin <branch name in remote repo>
   ```
   
 - Create a local repository and push a this new remote repository. Git remote add command helps to add information about the remote repository to the local repository. This is for importing a remote repo to an existing local repo instead of cloning the remote repo.
   ```bash
   git init
   git add <file>
   git commit -m "initial commit"
   git remote add origin <remote repository URL>
   git remote -v
   git push origin master
   ```


<a name="#Add-Commit-Push-Repository"></a>
Add, Commit and Push to remote Repository

 - Add files to staging area in a local repository  
   ```bash
   git add <file>
   # adds all untracked and modified files
   git add .
   ```
   
 - Create a local repository and push a this new remote repository. -m adds a message. commit -a combines the adds and commit command 
   ```bash
   git add <file>
   git commit -m "initial commit"
   git push origin master
   ```

 - Push changes from local to remote repository. -u flag sets up the local and remote branches. Origin is a shortcut name for the remote repository. master is the branch to push. We are pushing the default branch named master. Checking out a local branch from a remote branch automatically creates what is called a tracking branch. Tracking branches are local branches that have a direct relationship to a remote branch. If you’re on a tracking branch and type git push, Git automatically knows which server and branch to push to. Also, running git pull while on one of these branches fetches all the remote references and then automatically merges in the corresponding remote branch.
 
   ```bash
   git push -u origin master
   git push origin master
   ```
 - View the commit history
   ```bash
   git log
   git log --oneline
   # limit to 2 latest commits
   git log --oneline -2 
   ```

<a name="#Git-Status"></a>
Git Status
 - View the status of the files in working tree and staging area. Untracked files are files not in staging area.
   ```bash
   git status
   # short status
   git status -s
   ```
<a name="#Git-Tags"></a>
Git Tags
 - View the status of the files in working tree and staging area. Untracked files are files not in staging area.
   ```bash
   # To view all tags
   git tag
   # -a helps to create an annotated tag 
   git tag -a -m "message" <name of the tag>
   # To view a specific tag
   git tag v0.1
   # To push tag to remote repo
   git push origin v0.1
   # To create a temporary tag
   git tag -a -m "just a temp tag" temp HEAD~
   git tag -d temp
   ```
<a name="#Git-Branch"></a>
Git Branch
 - To create a new branch in local repository
   ```bash
   # two command approach
   git branch <feature branch name>
   git checkout <feature branch name>
   # one command approach
   git checkout -b <feature branch name>
   ```
 - To delete a new branch in local repository
   ```bash
   # switch to another branch first
   git checkout master 
   git branch -d <feature branch name>
   ```
 - To rollback the commits or branches deleted
   ```bash
   # to see the list of commits made
   git reflog
   # copy the SHA-1 code for the commit made
   git checkout -b <branch name> <SHA-1>
   ```

<a name="#Create-file-on-Git-Bash"></a>
Creating a file on Git Bash
 - To create a new file in local repository using Git Bash
 - Using Git command touch, only creates the file 
   ```bash
      newFile.txt
   ```
 - Using Git command echo, only creates the file 
   ```bash
      echo > <new_file.txt>
      echo "Added another line to file" >> <file_name.txt>
   ```
 - Using Git command cat, only creates the file and can start appending to the file
   ```bash
      cat > newFile.txt
   ```
 - Using Git command vim, only creates the file and can start editing to the file. To use the text editor, press Escape to exit insert mode and then type :wq (write/save and quit, or :q! if you want to cancel and return to the prompt).
   ```bash
      vim newFile.txt
   ```

<a name="#Git-Merge"></a>
Merging branches on Git Bash
  - To merge two branches 
   ```bash
      git checkout <destination-branch-name>
      git merge <source-branch-names>
   ```
   - To merge commit two branches. This creates a non-linear history.
   ```bash
      git checkout <destination-branch-name>
      git merge --no-ff <source-branch-names>
   ```


<a name="References"></a>
## References

[1] Version Control with Git, Coursera (Website: [coursera/git](https://www.coursera.org/learn/version-control-with-git/))

[2] Git tutorial, Atlassian (Website：[atlassian/git](https://www.atlassian.com/git/tutorials/learn-git-with-bitbucket-cloud))

[3] Git Official Document (Website：[git official document](https://git-scm.com/docs))
