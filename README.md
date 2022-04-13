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
