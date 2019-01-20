# Markdown Cheatsheet
https://github.com/adam-p/markdown-here/wiki/Markdown-Cheatsheet

# Git Commands Cheatsheet
Created and edited by Onlyuuuuuuuuuuuuuuuuuuuuuuuuu!

To add global configuration:

```$xslt
git config --global user.name "Anh Nguyễn"
git config --global user.email "duyanhnguyenngoc97@gmail.com"
git config --global core.editor "subl -w"
git config --global credential.helper store
git config credential.helper cache 3600
```
Alternative email:
```$xslt
git config --global user.email "15110007@student.hcmute.edu.vn"
```
Or edit ~/.gitconfig:
```$xslt
[user]
	email = duyanhnn@github.com
	name = Anh Nguyễn
[core]
	editor = subl -w
```
**Remember! Email + password with github.com domain is NOT used for log in, it can only be used to generate access token for pulling, fetching, pushing, etc... API using commands**

Clone with specific branch (ex: master) to a specific folder (ex: git-tranining-master):
```$xslt
git clone -b master https://github.com/duyanhnn/Git-Training.git git-tranining-master
```
Initialize:
```$xslt
git init (for current directory)
git init <directory> (for any directory)
git remote add origin https://github.com/duyanhnn/Git-Training.git
```
To change origin URI:
```$xslt
git remote set-url origin https://github.com/duyanhnn/Git-Training.git
```
For existed remote branch, fetch first (usually run after $(git checkout -b <branch>) and $(git remote add origin <URI>)), fetch will fetch all existed current branches:
```$xslt
git fetch
```
Or for only 1 specific branch
```$xslt
git fetch origin <branch>
```
Pull from specific branch (ex: master):
```$xslt
git pull origin master
```
Set up so that your local master branch tracks github master branch as an upstream (mapping between local branch & remote branch),
to set upstream, branch must existed in set of local branches:
```$xslt
git branch --set-upstream-to=origin/<remote branch> <local branch>
git branch -u origin/<remote branch> <local branch>
```
To unset upstream, use:
```$xslt
git branch --unset-upstream <local branch>
```
**It is recommended that you name your local branch the same as remote branch**

Then you can use pull and push with default upstream config
```$xslt
git pull
git push
```
Or set upstream when push (remote branch will automatically be created if not existed)
```$xslt
git push -u origin <remote branch>
```
For unrelated histories error:
```$xslt
git pull --allow-unrelated-histories
git pull origin <branch> --allow-unrelated-histories
```
For information about tracking and upstream, use one or more of the following commands:
```$xslt
git status
git branch -vv -a
```
Specific upstream information
```$xslt
git branch -vv -a
git remote show origin
```
**Remember! Big capital letter (in command's flag) means with FORCE! Use with caution!**

For renaming a branch (-M flag is for force rename):
```$xslt
git branch -m <old> <new>
git branch -M <old> <new>
```
For renaming current branch (-M flag is for force rename):
```$xslt
git branch -m <new>
git branch -M <new>
```
For removing a branch (-D flag is for force remove):
```$xslt
git push --delete <remote> <branch>
git branch -d <local branch>
git branch -D <local branch>
```
For 
