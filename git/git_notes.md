# Git Version Control

## Git configuration

- System configuration
- User configuration
- Project configuration

### System configuration

Set username: `git config --global user.name "User name"`

Set email: `git config --global user.email "email@address.com"`

List all the configuration: `git config --list`

Find current username: `git config user.name`

Find current email: `git config user.email`

Add vs code as a core editor for git: `git config --global core.editor "code --wait"`

Enable color ui for git: `git config --global color.ui true`

> Notes:
>
> - These commands will make change in **.gitconfig** file
> - Besides accessing a project's .git/config file, we can change its contents with: `git config` with no option

## Git Help

General command to find help: `git help`

Find help for particular git command: `git help your-command`

## Initialization

Initialize project with git(It will create .git directory which contains various files to keep track of changes): `git init`

## Steps to add commit

- Make change in any file of your project
- Add file to git(Stage your changes): `git add .` (here .(dot) tells add any changes in current directory's file)
- Commit files: `git commit -m "your message"`

## Git log

1. `git log`: find list of changes made with commits
2. `git log -5`: return recent 5 commits
3. `git log --since=2022-04-19`: return all commits done from 2022-04-19
4. `git log --author="User Name"`: return commits by author name
5. `git log --grep="Init"`: return commits that contains Init string in commit message.Here grep stands for global regular expression. It helps to search using commit message
6. `git log --oneline`: Show all commit with shart description.
7. `git log --oneline --decorate --graph --all`: Vusial view of branches and commits

example,
Which will output the log for all of Karen's commits labeled "refactor" during March 2019?

`git log --since=2019-03-01 --until=2019-03-31 --author="Karen" --grep="refactor"`

## Architecture

Git use three tree architecture

- Working directory
- Staging area/index
- Git repository
- Remote repository(Github) **Not apart of git architecture**

## Git Status

`git status`: Status of working directory like if any file added or modified

## Git Diff

`git diff`: Compares the changes to working directory files to the staging index

`git diff --staged`: Compares staged files to the repository versions.

`git diff --color-words`: Show difference with color

`git diff <first-commit-SHA>..<second-commit-SHA>`: Compare two commit

> Note: Here **..** is a part of syntax

## Delete file

`git rm file-name`: Delete file from git repository

## Move and Rename file

`git mv old-file-name new-file-name`: Rename the file

## Git show

`git show commit-id<Not required entire SHA value, only few first characters>`: Show what changes you have made in this commit

example,

`git show 14cA0W --color-words`

## Undo working directory changes

`git checkout -- <file>`: git checkout replaces the working directory version of a file with the git repository version of the file

example,
`git checkout 53daff9b -- about.php`: git checkout will pull the version of about.php from the needed commit, and that version will be included in the new commit.

## Unstage

`git reset HEAD <file>`: Unstage non-committed files from staging area

## Amend commits

Git allows to make changes in only last commit.

`git commit --amend -m "New message"`: It amend the previous commit and merge the current changes with it and update the message and have new SHA value.

> Note: We can also use this command to change commit message

## Retrieve old version

`git revert <commit SHA>`: This will revert our changes to provided commit and create new commit

## Remove untracked files

`git clean -n`: Would remove untracked files from working repository

`git clean -f`: Remove untracked files from working repository

## List the files tracked by git

`git ls-tree HEAD`: This will list all the file tracked by git till HEAD

## Track empty directory

By convention developer create empty file with name .gitkeep in empty directory
