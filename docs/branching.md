# Branching
## Rename a branch
```
git branch -m <old_name> <new_name>
```
## Copy a branch
```
git branch -c <branch_source> <new_branch>
```
## Delete a branch
```
git branch -d <branch_name>
```

## Copy/Move commits from one branch to another
This can happen when you switch between branches and unknowingly committed your intended changes in the wrong branch! No panic, you can copy the commits across and delete the mistaken commits.
1. Copy the commit number in the mistaken branch
```
git log --oneline
```
2. Go to the correct branch
```
git checkout <correct_branch_name>
```
3. Cherry-pick the commit in the mistaken branch
```
git cherry-pick <commit_number_from_mistaken_branch>
```
4. Delete the commit in the mistaken branch 
```
git checkout <mistaken_branch_name>
```
```
git reset --hard <commit_number>
```
or 
```
git reset --hard HEAD~1
```

[back to Contents](https://github.com/rtaylor02/git-master/blob/main/README.md)
