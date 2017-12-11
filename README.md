
Q) How to initialize git inside existing project?
A) Inside root directory of your project
```bash
$ git init .
```
___
Q) How to add file to git ?
A)
```bash
$ git add <file_name>
        or
$ git add --all  //add all files

```

___
Q) How to commit changes to git ?
A) add files first then
```bash
$ git commit -m "commit message here"
```

___
Q) How to add remote repository to project ?
A)
```bash
$ git remote add <remote_name> git@server.domain:user/projectName.git
        or
$ git remote add <remote_name> https://server.domain/user/projectName.git
```
<remote_name> maybe origin,upstream, etc
___
Q) How to push local Repo to Remote ?
A)
```bash
$ git push <remote_name> <branch_name>
        or
$ git push <remote_name> --all //push all branches
```
___
Q) How to pull from Remote?
A) make sure locally your on the same branch
```bash
$ git pull <remote_name> <branch_name>
```
___
Q) how to merge branch to master ?
A)
```bash
$ git checkout master
$ git merge <branch_name>
```
use --no-commit flag to avoid auto commit merge.
___
Q) How to know currently working branch?
A)
```bash
$ git status
```
___
Q) How to create new branch ?
A) create new branch from current branch
```bash
   $ git checkout -b <branch_name>
```

Q) How to rename local branch ?
A)
```bash
$ git branch -m <new-name>  //within the branch
                or
$ git branch -m <old-name> <new-name>  //from other branch
```
___
Q) How to delete local branch ?
A)
```bash
$ git branch -d <branch_name>
        or
$ git branch -D <branch_name>  //force delete
```

___
Q) How to delete remote branch ?
A)
```bash
$ git push <remote_name> --delete <branch_name>
        or
$ git push <remote_name> :<branch_name>
```
___
Q) How to switch between existing branches?
A)
```bash
$ git checkout <branch_name>ToSwitch
```
   Note : git ignored fields are common for all branches.
___
Q) How to create new branch form old-commit ?
A)
```bash
$ git checkout -b <branch_name> <commit>
```
Note: example commit 0d1d7fc32
___
Q) How to roll back to particular commit ?
A)
```bash
$ git revert <commit>
        or
$ git revert --no-commit <commit>..HEAD
$ git commit
```
you can also use flag --no-edit instead of --no-commit
___
Q) How to uncommit ?
A)
```bash
$ git reset --soft HEAD~1
```
NOTE: HEAD~1 for last commit, HEAD~3 for last 3 commit.
___
Q) How to unstage single file ?
A)
```bash
$ git reset <file_name>
```
___
Q)How to list all commits ?
A)
```bash
$ git log
        or
$ git log -<limit>  // limit = 5 for listing last 5 commits
```
___

Q) How to preserve changes made in local while pulling from remote ?
A) Using git stash (use more advance options/flags for more control)
```bash
$ git stash clear
$ git stash
$ git pull
$ git stash pop
```
___

Q) How to see List of stashed files ?
A)
```bash
$ git stash show
```





































