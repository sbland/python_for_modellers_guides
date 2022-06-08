# Version Control(git)

Version control is used to log changes to a file or directory. It allows easily sharing, reverting and explaining changes.
This document is intended as a quick start guide to using git in your project. For more indepth guidance try the links below:
https://www.atlassian.com/git/tutorials/learn-git-with-bitbucket-cloud
https://git-scm.com/doc


## Glossary of terms

 - *git repo* - Also known as a git repository or just a repo. This is the name of a directory that has version control setup.
 - *git commit* - A git commit is a group of changes that are saved to the repo. 
 - *merge conflict* - Your changes may overrides someone else changes if you merge the files together.

## Using Git

### Git init

To turn a directory into a git repo(I.e a directory with version control) you need to run `git init`. This will add a hidden folder named `.git` that contains all the git settings.


### Git clone

You can also copy an existing repo by using `git clone <REPO URL>`. The url can be obtained from the repo's website. For Github click the green `code` button and copy the url from here.

### Using branches

Your repository by default contains a single branch named **main** or **master**. This branch is a list of all the commits since the start of the repository.
It is recommended to create a seperate working or feature branch that you work on until you are sure of all your changes.
To create a branch locally run `git checkout -b <BRANCH_NAME>` replace <BRANCH_NAME> with a name of your choice. 
You can then work on this branch without worrying about braking the main branch. You should push this branch to the remote repository then use a *pull request* to merge it with the main branch.

### Making changes

To make changes to a repository there are a number of steps:

`changes -> add -> commit -> push`

1) Make any required changes to the files
2) Use the command `git add *` to add all changes to the current *stage*. You can run this command multiple times until you are happy with all your changes.
3) Once you are happy with your changes you can run `git commit -m "ADD A DESCRIPTION HERE"`. This will save all your changes to a commit.
4) You can now push all your changes to the remote url using `git push`.

### Pull Remote Changes

When changes have been made to the repository by someone else you need to pull the changes to your local system. 
To do this use the command `git pull`. It is best to do this when you have no local file changes that have not been commited.

#### Merge conficts
If you have changed any files locally that have also been changed remotely you will have merge conflicts.
Before you can push your changes to the remote repo you will need to resolve any conflicts in your files. 
Git will inform you of any files with conflicts. To continue go into these files then find a merge conflict like the example below.
Modify the file to resolve the conflict then save the file.

Example merge conflit (from https://www.atlassian.com/git/tutorials/using-branches/merge-conflicts)
```
<<<<<<< HEAD
this is some content to mess with
content to append
=======
totally different content to merge later
>>>>>>> new_branch_to_merge_later
```

### Pull Requests(Merging your branch changes with main)
Once you have completed work on a feature/update on your own branch you need to merge it back into the main branch.
If you are working on the repo on your own you can simply switch to the main branch with `git checkout main` then merge your branch
with `git merge <BRANCH_NAME>`.
If you are working as part of a team it is best to use pull requests. These involve requesting the the repo admin/maintainer merges your code into the main branch.
More information on pull requests can be found here: https://www.atlassian.com/git/tutorials/making-a-pull-request

### Authorization (HTTPS or SSH)

Public repositories can be accessed using `git clone` above but private repositories require an extra step.

It is recommended to setup a ssh key to allow secure access to private repositories.

#### SSH
To setup your access key follow the instructions here: https://docs.github.com/en/authentication/connecting-to-github-with-ssh
(If using a linux terminal such as Git Bash make sure to use the linux instructions)

Instead of setting up the ssh-agent you can create a file in your home directory*  `~/.ssh/config` with the following contents:
```sh
host github.com
  HostName github.com
  IdentityFile ~/.ssh/id_rsa # Replace id_rsa with the keyname you created
  User git
  IdentitiesOnly yes
```

## Helpful Tools

### Vscode

Visual studio code has a number of features that make using git easier. Opening a version controlled directory will enable these features.
It is also recommended to add the vscode extension **git graph** to allow visualizing commits to the repository
