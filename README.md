# Markdown Cheatsheet
https://github.com/adam-p/markdown-here/wiki/Markdown-Cheatsheet

# Git Commands Cheatsheet
Created and edited by Onlyuuuuuuuuuuuuuuuuuuuuuuuuu!

To add global configuration:

```$xslt
git config --global user.name "Duy Anh"
git config --global user.email "duyanhnguyenngoc97@gmail.com"
```
Alternative email:
```$xslt
git config --global user.email "15110007@student.hcmute.edu.vn"
```
Clone with specific branch (ex: master) to a specific folder (ex: git-tranining-master):
```$xslt
git clone -b master https://github.com/duyanhnn/Git-Training.git git-tranining-master
```
Initialize:
```$xslt
git init
git remote add origin https://github.com/duyanhnn/Git-Training.git
```
To change origin URI:
```$xslt
git remote set-url origin https://github.com/duyanhnn/Git-Training.git
```
Pull from specific branch (ex: master):
```$xslt
git pull origin master
```
Or set up so that your local master branch tracks github master branch as an upstream (mapping between local branch & remote branch),
to set upstream, branch must existed in set of local branches:
```$xslt
git branch --set-upstream-to=origin/<remote branch> <local branch>
```
For example
```$xslt
git branch --set-upstream-to=origin/master master
```
For existed remote branch, fetch first (usually run after $(git checkout -b <branch>)):
```$xslt
git fetch
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
git pull origin <branch> --allow-unrelated-histories
```
For example:
```$xslt
git pull --allow-unrelated-histories
```
For information about tracking and upstream, use one or more of the following commands:
```$xslt
git status
git branch --all
```
Specific upstream information
```$xslt
git branch -vv
git remote show origin
```
For removing a branch:
```$xslt
git push --delete <remote> <branch>
git branch -d <local branch>
```
For example:
```$xslt
git push --delete origin branch_test_2
git branch -d branch_test_2
```
Or use -D flag to force remove (on local):
```$xslt
git push --delete origin branch_test_2
git branch -D branch_test_2
```
