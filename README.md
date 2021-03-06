# Markdown Cheatsheet
https://github.com/adam-p/markdown-here/wiki/Markdown-Cheatsheet

# Git Commands Cheatsheet
Created and edited by Onlyuuuuuuuuuuuuuuuuuuuuuuuuu!

## Part I: Git Configurations
To add global configuration:

```$xslt
git config --global user.name "Anh Nguyễn"
git config --global user.email "duyanhnguyenngoc97@gmail.com"
git config --global core.editor "subl -w"
git config --global credential.helper store
git config credential.helper cache 86400
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
[credential]
	helper = store
```
**Remember! Email + password with github.com domain is NOT used for log in, it can only be used to generate access token for pulling, fetching, pushing, etc... API using commands.**

**Only store git credentials in plain text in your personal computer. For storing your credentials in SSH key, see instruction below.**

## Part II: Git Initialization
Clone with specific branch (ex: master) to a specific folder (ex: git-tranining-master):
```$xslt
git clone -b <branch> https://github.com/duyanhnn/Git-Training.git <folder>
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
**It is recommended that you name your local branch the same as remote branch.**

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

## Part III: Git Informations
For information about tracking and upstream, use one or more of the following commands:
```$xslt
git status
git ls-files
git branch -vv -a
```
Specific upstream information
```$xslt
git branch -vv -a
git remote show origin
```

## Part IV: Git Managing Files
To update any changes outside of git (using bash command or file manager to rename, change levels, ...):
```$xslt
git add -A
```
To update tracked files (rename, change levels, ...):
```$xslt
git add -u
```
To delete a file tracked by git (without delete in local directory, remove the "cached" flag), remember to use FORCE flag (-f) with caution:
```$xslt
git rm -f --cached <file name>
git rm -rf --cached <directory name>
```

To combine $(git add .) and git commit use (only tracked files, untracked files must be added manually):
```$xslt
git commit -a
git commit -am "<messages>"
```
To abort file changed (not yet added in staging area), use:
```$xslt
git checkout -- <file name>
```
To abort file added in staging area (after $(git add .)) and send back to unstaging area, but still keep changes of course, use:
```$xslt
git reset HEAD <file name>
```
To see commit history (press q to quit):
```$xslt
git log
git log --abbrev-commit
git log --oneline --graph --decorate
git log --since="3 days ago"
git log -- <path to file | file name>
git show <commit id>
```

## Part V: Git Branches
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

## Part VI: Git Aliases
**This section is only preserved for GIT ALIASES**

Create an alias
```$xslt
git config --global alias.<name> "<command without git prefix>"
```
Or add directly to .gitconfig
```$xslt
[alias]
	logfull = "log --oneline --graph --decorate"
```