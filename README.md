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



<a name="repository"></a>
Create a local Repository


 - Clone (download) a repository that already exists on GitHub, including all of the files, branches, and commits

   ```bash
   git clone [url]
   ```

## References

[1] Version Control with Git, Coursera (Website: [coursera/git](https://www.coursera.org/learn/version-control-with-git/))

[2] Git tutorial, Atlassian (Website：[atlassian/git](https://www.atlassian.com/git/tutorials/learn-git-with-bitbucket-cloud))

[3] Git Official Document (Website：[git official document](https://git-scm.com/docs))
