# Basic Commands
## Check status of your repository
```
git status
```

## Display commit history
```
git log
```
or
```
git log --oneline
```
> Shorter version of git log


## Add files - Untracked files become Staged files
```
git add [<file name>...]
```
or
```
git add .
```
> Stage **all** untracked files

## Restore changes of untracked files
```
git restore [<file name>...]
```
or
```
git restore .
```
> Restore **all** untracked files

## Unstage files
```
git reset <file name>
```

## Stash current modifications
You can save current modification (including untracked files) and return to clean working directory by stashing.
```
git stash push -u -k
```
> -u / --include-untracked

> -k / --keep-index

To apply most recently stashed modification:
```
git stash pop
```

## Fetch remote changes
```
git fetch <remote_reference>
```
## Push a local repo to GitHub (remote)
When you have a local project in your machine and you want to create a remote repo on Github:
1) Create a remote repository
2) Set remote origin on your local git repository
   ```
   git remote add origin <newly_created_git_remote_repo.git>
   ```
4) Rename your 'master' local branch to 'main'
   ```
   git branch -M main
   ```
5) Push your local repo to remote repo
   ```
   git push -u origin main
   ``` 

## Clone Remote Repo
```
git clone <repo_URL>
```
When a repo has very long name, this can be problematic in Windows OS. Use `-c core.longpaths=true` option:
```
git clone -c core.longpaths=true <repo_URL>
```
