
## Git pro book:
https://git-scm.com/book/en/v2

## Git concise material
https://git-scm.com/docs/gittutorial

## Git cheatsheet
https://training.github.com/downloads/github-git-cheat-sheet.pdf

## Git visual cheatsheet
https://ndpsoftware.com/git-cheatsheet.html#loc=index;

## Git Tutorials: 
- Download from here:
https://tutsnode.net/git-github-essentials-for-version-control-management/


![Have_Video](https://img.shields.io/badge/Let's_start!-OK-54b09f.svg)

### You may take a video reference (CodeWithHarry, indian youtuber)
https://youtu.be/gwWKnnCMQ5c

## Things we will learn :
 - Initializing repository
 - Making different files and folders
 - About `.gitignore`
 - About adding, commits(with some message)
 - Reverting the changes or mistakes made
 - Branches, switching in different branches
 - Frequently checking git status
 - Merging branches into main or master branch
 - About github and `cloning`
 - About `Readme.md` file of github
 - Uploading your local repository(in your computer) to github repository`(remote repository)`

## Main and general commands that we use mostly.
- Refer to book for the required command if not found here.
```diff
 git init---------------------------------------- (start your repository)
 git status-------------------------------------- (check status)
 git status -s ---------------------------------- (short status check)
 git checkout yourfilename.extension------------- (undo uncommitted changes)
 git checkout -f -------------------------------- (undo uncommitted changes forcely)
 git branch ------------------------------------- (check which branch you are in)
 git branch branch_name ------------------------- (create a branch)
 git checkout branch_name ----------------------- (move to that branch)
 git switch branch_name ------------------------- (move to that branch)
 git merge branch_name--------------------------- (merge the branch in current branch)
 git rm --cached filename------------------------ (remove the files from staging area)
 git log ---------------------------------------- (to view your log history containing your commit history)
 git log --pretty=oneline ----------------------- (to view log in oneline format)
 git log -p -1 ---------------------------------- (shows last log)
 git log -p -2 ---------------------------------- (shows last two logs)
 git log --oneline ------------------------------ (shows each log commits in oneline)
 git remote add origin GitProfileLink ----------- (connecting to remote repository)
 git push origin master-------------------------- (push to remote repository)
 git push -u origin master ---------------------- (creating upstream for branch master here)
 git push---------------------------------------- (directly push if upstream is created)
 touch somefile --------------------------------- (make file using touch)
 mkdir------------------------------------------- (make new directory or folder)
 rmdir ------------------------------------------ (remove or delete directory)
```


## Git
- Git is a free and open source distributed version control system designed to handle everything from small to very large projects with speed and efficiency.
- It is a version control systen (VCS).

## Commit
- Git commit actually means record changes to the repository. 
- commitis just a snapshot of a moment. 
- when you commit, you do not copy, paster or overwrite files, only tracks the changes that happens to file or files and modify them.

Note: main/master branch, both are same

## Head
- You can think it as a current branch.
- working with git, only one branch can be checkedout at a time.
- This is called the head branch.
- Also called active or currnt branch.
- You can check it by 
```diff
 cat .git/HEAD
 ```
 - OR you may open HEAD file, inside .git directory where HEAD is currently pointing.

## Detached HEAD
- In rare cases, the head file doesn't contain the branch reference.
- Detached head occurs when you check out a commit that is not in a branch.
- The term detached head tells you that you are not viewing a head of any repository, and the head is most recent version of a branch. It is something called the tip of the branch.

Note: 1. ```diff git switch branchname ``` is similar to ```diff git checkout branchname ```
      2. ```diff git switch -c branchname``` is similar to ``diff git checkout -b branch```
         -to create and switch branch at sametime
         
## git ls-files
```diff
git ls-files
```
- shows files in staging area

## For restoring changes
```diff
git restore filename.extension 
```
- to undo changes in the given files
```diff
git restore . 
```
- to undo all changes in all files

Equivalent:
```diff 
git checkout filename.extension 
```
- to undo changes in the given files
```diff
git checkout . 
```
- to undo all changes in all files
      
## Clean
```diff
git clean -dn 
```
- removes files but shows for us what will be removed
```diff
git clean -df 
```
- will remove newly created unstaged files forcely i.e. done forcely(df) 
  
## Text Editors you can use (based on linux)
CAT
```diff
cat > test.txt
```
- will create file and wait for the input
- ctrl+c
- to get out of file or close file while using cat
 
 ECHO
 ```diff 
 echo "your text">filename.extension
 ```
  ```diff
  e.g. echo "hello folks">test.txt
  ```
```diff
echo null>filename.extension 
```
- for nothing inside file

VIM
```diff
vim filename.extension 
```
- to create file of given extension
```diff
vim filename.extension
```
- to view file
  
 Note: (press i to insert text inside file after opening the file)
       (press escape i.e. esc and type :wq to save and quit from file)

TOUCH COMMAND
```diff
touch filename.extension
```
- to create file of the given extension

## RESTORE (from staging area)
```diff 
git restore --staged filename
```
- to restore the given file
```diff
git restore --staged . 
```
- to resttore all files from staging area

## Reset
- There are three types of reset and they are
 1. soft reset
 2. default reset
 3. hard reset

```diff
git reset --soft HEAD~1
```
- only resets the commit i.e. one commit will be removed but file is still in staging area
- You can check it by 
```diff 
git ls-files
```
```diff  
git reset HEAD~1
```
- (undo one commit and also undo files from staging area)
  
```diff
  git reset --hard HEAD~1
```
- (undo one commit, undo files from staging area and removes file from working directory as well)


## revert
```diff
  git revert <commit id>
```
- removes the changes of commit (commit id) from your current HEAD  and asks for new commit message to create new commit having current head things with no (commit id) things 
- for reference https://www.theserverside.com/tutorial/How-to-git-revert-a-commit-A-simple-undo-changes-example
