# Installation and Setup
## Installation
Based on your operating system, follow official guide [here.](https://git-scm.com/book/en/v2/Getting-Started-Installing-Git)
Once installed, check from command line:
```
git --version
```
![CLI - git version](../img/git_version.png)

## Local Setup
To know the location of your git configuration file (.gitconfig):
```
git config --list --show-origin
```
To edit your git configuration using Visual Code (arbitrary), enter the full path as the parameter:
```
code ~/.gitconfig
```
> In the sample above, the location of the configuration file is ~/.config.
Alternatively, you can modify .gitconfig file via CLI if you know the elements to set. E.g. to change username and email address:
```
git config --global user.name "Rod Taylor"
git config --global user.email "git-master@mail.com"
```
To initialise a local repository, type the command below in the repository folder. This will create a hidden .git folder inside the repo:
```
git init
```
If you want Git to exempt certain files or directories from being tracked, specify them in .gitignore file. Create .gitignore file in root of your repo:
```
code .gitignore
```

## Remote Setup
Remote here means GitHub repository that is linked/referenced by your local repo.
Your remote repo can exist before (push), or after (pull) you create your local.
```mermaid
flowchart LR
A[local repo] --push--> B[GitHub repo]
```
```mermaid
flowchart LR
A[GitHub repo] --pull--> B[local repo]
```
Once you initialise a local git repository, check if that repo linked to any remote repo:
```
git remote -v
```
> **-v:** verbose

![CLI - git remote](../img/git_remote_v.png)

To link your local repo to a remote repo:
```
git remote add <remote reference> <remote url>
```

Remote reference is named, by default, to `origin`. Use command below to rename. E.g. from `origin` to `main`:
```
git remote -rename origin main
```
To push your branch's new commits to remote repo branch:
```
git push -u <remote reference> <remote branch>
```
> **-u:** --set-upstream. You only need to set upstream once at your first push.
E.g.
```
git push -u origin main
```
![CLI - git push](../img/git_push_origin_main.png)

[return to Contents](https://github.com/rtaylor02/git-master/blob/main/README.md)

# My Scratch Pad
> **Note:** This is a note

```

3 back-ticks: This is code

```

`This is highlighted`

```mermaid
sequenceDiagram
Rod -> Kasia: Hello
Rod --> Adam: Halo!
Adam -->> Rod: Selamat pagi, papa!
Rod -x Adam: Selamat pagi, sayang!
Adam --x Kasia: Dzien dobry, mamo!
```
```mermaid
gitGraph
commit
commit
branch dev
checkout dev
commit
commit
branch feat/feature-1
checkout feat/feature-1
commit
commit
checkout dev
merge feat/feature-1
checkout main
commit
checkout dev
commit
```

```mermaid
graph LR
A[Untracked] --git add . ---> B[Staged] --git commit ---> C[Committed]

```
