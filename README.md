## Table of Contents

[Repository and Working Directory](#Repository and Working Directory)

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
  3. [Commit Repository](#Commit-Repository)
  3. [Working Directory](#working-directory)



[References](#references)

<br />

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
   git clone [url]
   ```

 - Create a local repository and push a to a remote repository that already exists on GitHub with new commits
   ```bash
   git clone [url]
   git add <file>
   git commit -m "message"
   git push origin <branch name in remote repo>
   ```
   
 - Create a local repository and push a this new remote repository
   ```bash
   git init
   git add <file>
   git commit -m "initial commit"
   git remote add origin <remote repository URL>
   git remote -v
   git push origin master
   ```


<a name="#Commit-Repository"></a>
Commit to Repository

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
   ```

   
<a name="References"></a>
## References

[1] Version Control with Git, Coursera (Website: [coursera/git](https://www.coursera.org/learn/version-control-with-git/))

[2] Git tutorial, Atlassian (Website：[atlassian/git](https://www.atlassian.com/git/tutorials/learn-git-with-bitbucket-cloud))

[3] Git Official Document (Website：[git official document](https://git-scm.com/docs))
