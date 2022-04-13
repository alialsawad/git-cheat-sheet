# Git Cheat Sheet

### Index

- [Set Up](#setup)
- [Create](#create)
- [Local Changes](#local-changes)
- [Search](#search)
- [Commit History](#commit-history)
- [Move / Rename](#move--rename)
- [Branches & Tags](#branches--tags)
- [Update & Publish](#update--publish)
- [Undo](#undo)

<hr>

## Setup

##### Show current configuration:

Shows user.name, user.email, remote origin url and more

```
$ git config --list
```

##### Set a global name:

```
$ git config --global user.name "<user.name>"
```

##### Set a global email address:

```
$ git config --global user.email "<user.email>"
```

<hr>

## Create

##### Download an existing repository:

```
$ git clone
```

##### Initiate git in local environment:

```
$ git init
```

<hr>

## Local Changes

##### Changes in local directory:

```
$ git status
```

##### Shows the difference between repo and local files:

```
$ git diff
```

##### Add all changes:

```
$ git add .
```

##### Add some changes in &lt;file&gt; to the next commit:

```
$ git add -p <file>
```

##### Add only the mentioned files to the next commit:

```
$ git add <filename1> <filename2>
```

##### Commit all local changes in tracked files:

```
$ git commit -a
```

##### Commit previously staged changes:

```
$ git commit
```

##### Commit with message:

```
$ git commit -m 'message here'
```

##### Combine add and commit commands:

```
$ git commit -am 'message here'
```

##### Commit to some previous date:

```
$ git commit --date="`date --date='n day ago'`" -am "<Commit Message Here>"
```

##### Change last commit:<br>

<em><sub>Don't amend published commits!</sub></em>

```
$ git commit -a --amend
```

##### Change last commit and keep log message:

<em><sub>Don't amend published commits!</sub></em>

```
$ git commit --amend --no-edit
```

##### Change committer date of last commit:

```
GIT_COMMITTER_DATE="date" git commit --amend
```

##### Change Author date of last commit:

```
$ git commit --amend --date="date"
```

##### Move uncommitted changes from current branch to some other branch:<br>

```
$ git stash
$ git checkout branch2
$ git stash pop
```

##### Restore stashed changes back to current branch:

```
$ git stash apply
```

#### Restore particular stash back to current branch:

- _{stash_number}_ can be obtained from `git stash list`

```
$ git stash apply stash@{stash_number}
```

##### Remove the last set of stashed changes:

```
$ git stash drop
```

<hr>

## Search

##### A text search on all files in the directory:

```
$ git grep "Hello"
```

##### In any version of a text search:

```
$ git grep "Hello"
```

<hr>

## Commit History

##### Show all commits, starting with newest (it'll show the hash, author information, date of commit and title of the commit):

```
$ git log
```

##### Show all the commits(it'll show just the commit hash and the commit message):

```
$ git log --oneline
```

##### Show all commits of a specific user:

```
$ git log --author="username"
```

##### Show changes over time for a specific file:

```
$ git log -p <file>
```

##### Who changed, what and when in &lt;file&gt;:

```
$ git blame <file>
```

##### Show Reference log:

```
$ git reflog show
```

##### Delete Reference log:

```
$ git reflog delete
```

<hr>

## Move / Rename

##### Rename a file:

Rename Index.txt to Index.html

```
$ git mv Index.txt Index.html
```

<hr>

## Branches & Tags

##### List all local branches:

```
$ git branch
```

#### List local/remote branches

```
$ git branch -a
```

##### List all remote branches:

```
$ git branch -r
```

##### Switch HEAD branch:

```
$ git checkout <branch>
```

##### Checkout single file from different branch

```
$ git checkout <branch> -- <filename>
```

##### Create and switch new branch:

```
$ git checkout -b <branch>
```

##### Switch to the previous branch:

```
$ git checkout -
```

##### Create a new branch from an exiting branch and switch to new branch:

```
$ git checkout -b <new_branch> <existing_branch>
```

#### Checkout and create a new branch from existing commit

```
$ git checkout <commit-hash> -b <new_branch_name>
```

##### Create a new branch based on your current HEAD:

```
$ git branch <new-branch>
```

##### Create a new tracking branch based on a remote branch:

```
$ git branch --track <new-branch> <remote-branch>
```

##### Delete a local branch:

```
$ git branch -d <branch>
```

##### Rename current branch to new branch name

```
$ git branch -m <new_branch_name>
```

##### Force delete a local branch:

<em><sub>You will lose unmerged changes!</sub></em>

```
$ git branch -D <branch>
```

<hr>

## Update & Publish

##### List all activities:

```
$ git remote -v
```

##### Show information about a remote:

```
$ git remote show <remote>
```

##### Add new remote repository, named &lt;remote&gt;:

```
$ git remote add <remote> <url>
```

##### Rename a remote repository, from &lt;remote&gt; to &lt;new_remote&gt;:

```
$ git remote rename <remote> <new_remote>
```

##### Remove a remote:

<em><sub>Note: git remote rm does not delete the remote repository from the server. It simply removes the remote and its references from your local repository.</sub></em>

```
$ git remote rm <remote>
```

##### Get all changes from HEAD to local repository:

```
$ git pull origin master
```

##### Get all changes from HEAD to local repository without a merge:

```
$ git pull --rebase <remote> <branch>
```

##### Publish local changes on a remote:

```
$ git push <remote> <branch>
```

##### Delete a branch on the remote:

```
$ git push <remote> :<branch>
```

OR

```
$ git push <remote> --delete <branch>
```

<hr>

## Undo

##### Discard all local changes in your working directory:

```
$ git reset --hard HEAD
```

##### Undo the last `git add`:

```
$ git reset HEAD
```

##### Discard local changes in a specific file:

```
$ git checkout HEAD <file>
```

##### Revert a commit (by producing a new commit with contrary changes):

```
$ git revert <commit>
```

##### Reset your HEAD pointer to a previous commit and discard all changes since then:

```
$ git reset --hard <commit>
```

##### Reset your HEAD pointer to a remote branch current state.

```
$ git reset --hard <remote/branch> e.g., upstream/master, origin/my-feature
```

##### Reset your HEAD pointer to a previous commit and preserve all changes as unstaged changes:

```
$ git reset <commit>
```

##### Remove files that were accidentally committed before adding .gitignore:

```
$ git rm -r --cached .
$ git add .
$ git commit -m "remove xyz file"
```
