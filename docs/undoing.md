Most actions in Git results in another commit. Therefore it's (almost) always possible to revert or fix what you did wrong initially.

# Amend the previous commit message:
```
git commit --amend -m "This is the correct message"
```

# Restore changes in a file (including if you have deleted the file and want to retrieve it):
```
git restore <file_name>
```

# Add a file into a previous commit:
```
git add <file_name>
git commit --amend --no-edit
```

# Scrap all the uncommited changes you have done and go to previous state:
```
git reset --hard HEAD
```

# Remove commits and go back to certain commit number:
```
git reset --hard <commit_number>
```
**NOTE**: commit_number is where HEAD is going to be after this command, i.e. changes in that commit will be visible.

**Reset Mode**: 
- --hard ==> any changes in the commit are deleted
- --mixed ==> modified files are unstaged (default)
- --soft ==> modified files are staged

# Retrieve previously removed commits done by hard reset:
```
git reflog
git reset --hard <commit_number>
```
or
```
git reflog
git branch <new_branch_name> hash
```

# Retrieve previously deleted branch:
```
git reflog
git branch <branch_name> <commit_number>
```

# Move commit from one branch to another:
@ source branch where the commit is, note the commit number:
```
git checkout <source_branch>
```
@ destination branch where you want to move the commit to:
```
git checkout <destination_branch>
git cherry-pick <commit_number>
```

# Undo git reset using reflog:
When you do `git reset <SHA>`, then you bring back your repo to the state of <commit_id>. You cannot see this step in `git log`, but you can see it in `git reflog`.

Following a `git reset`, this is your `git log --oneline` looks like. Notice that reset is not listed here.  
![image](https://github.com/user-attachments/assets/b56ced71-cd2f-46ef-9477-5d367040f5c6)

To undo previous `git reset`:  
`git reflog`
With this command, you will see ALL the log history like below. Notice reset is also listed here..  
![image](https://github.com/user-attachments/assets/7189d77d-5baf-4b7f-98c3-257fd5f472ea)

Undo the previous `git reset` with another `git reset` (fight fire with fire!):  
![image](https://github.com/user-attachments/assets/f5effc69-895a-4f0d-9380-8668088ba2a4)

Result after this (phew!!)  
![image](https://github.com/user-attachments/assets/9d8cafb0-4707-409d-bdab-d8da601127d8)  

# Modify .gitignore file and re-apply the new 'rules'
Mid-way your work, you already some modified tracked changes and changes to be committed. You need to:  
1. Edit your .gitignore file and save
2. Remove all staged files: `git rm -r -f --cached .`. NOTE: only use -f if necessary, i.e. git will hint this.  
   ![image](https://github.com/user-attachments/assets/4dc6501f-5399-409a-8329-2f9fe393ca5a)  
   ![image](https://github.com/user-attachments/assets/5232e2a8-d344-46fc-8ea4-6d54c549d48a)  
3. Add and commit: `git add .` and `git commit -m "precious message"`
   
