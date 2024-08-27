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
**NOTE**: --hard ==> modified files are unstaged and unmodified; --mixed ==> modified files are unstaged (default) ; --soft ==> modified files are staged

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
