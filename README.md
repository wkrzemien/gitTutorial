0. Check your settings:
 * git version:

```
git --version
```

 * username, email, editor:

```
git config --list 
```

1. setup username, e-mail and editor

```
git config --global  user.name joan doe
git config --global  user.email joan.doe@uj.edu.pl
git config --global  core.editor vim
```

2. Create a folder myRepo and create an empty git repository in it.
Check the status and the history of log

```
mkdir myRepo
cd myRepo
git init 
git status
git log --graph --stats
```

3. Clone another repo from my github  https://github.com/wkrzemien/gitTutorial

```
cd ..
git clone https://github.com/wkrzemien/gitTutorial
cd gitTutorial
```

4. Add some new file and check the status  

```
cd gitTutorial
echo 'tests' > file3
git status
```

5. Modify the content of the file2 and check the status  

```
echo 'add some staff' >> file2
git status
```

6. Stage changes and check the status  

```
git add file2 file3
git status
```

7. Commit and check the status and commit history  

```
git commit
git status
git log --stat --graph
```

8. Rename the file1 to newFile1 and commit changes

```
mv file1 newFile1
git status
git add newFile1
git rm file1
git status
git commit
git log --stats --graph
git status
```

9. Modify the content of file2 stage it and modify its content again. What status do you see? 

```
echo 'blabla' >> file2 
git add file2 
git status
echo 'bleble' >> file2 
git status
git add file2 
git commit
git log --stats --graph
git status
```

10. Add a new file and commit it to the last commit (withouht creating a new commit)  

```
echo 'test test' > file4
git add file4 
git commit --amend
git log --stats --graph
git status
```

11. Go to myRepo add a remote repoistory to your  gitTutorial repo and fetch the content 

```
cd ../myRepo
git remote  add gitTutorial ../gitTutoral
git fetch gitTutorial
git remote -v
```

12. Create a new branch develop (in gitTutorial repo) add some changes there and merge its content to master, finally delete the branch  

```
cd ../gitTutorial
git branch develop
git checkout develop
touch file6
git add file6
git commit
git status
git log
git checkout master
git status
git log
git merge develop --ff-only
git status
git log
git branch -d develop
```

13. Create brach test and push it to your myRepo
  
```
git remote  add myRepo ../myRepo
git branch test
git checkout test
git push myRepo test
cd ../myRepo
git checkout test
git status
git remote -v
ls
```
