# Git cheat sheet

| git |  version 2.7.4 |
|-----|----------------|

### Basic git setup :
#### These will be reflected as Author details in each commit you make

#### Global config:
| Command |
|---------|
| `$ git config --global user.name "your_username"` |
| `$ git config --global user.email "your_email"`	|

#### Local config:
| Command |
|---------|
| `$ git config  user.name "your_username"` |
| `$ git config  user.email "your_email"`	|

### Adding git to project:
| Command | Description |
|---------|-------------|
| `$ git init .` | Initialize git inside project root directory. |
| `$ git add .` | Stage all files for commit. |
| `$ git commit -m "commit-message"` | Commit staged files to git. |

### Adding Remote repo to Project:
| Command | Description |
|---------|-------------|
| `$ git remote add <remote_name> <remote_address>` | add remote repository where<br>remote_name: origin,upstream etc<br> remote_address:(url) gethub, bitbucket etc |
| `$ git remote remove <remote_name>` |	delete remote |
| `$ git push <remote_name> <branch-name>` | push all the commits to remote default branch name master |

### Synchronizing local with remote (upstream):
| Command | Description |
|---------|-------------|
| `$ git fetch` | Download changes from remote without making any changes to files in the working directory. |
| `$ git pull` | Download others commits from remote and apply to working directory. |
| `$ git push` | Upload local commits to remote. |

### Branches in git:
| Command | Description |
|---------|-------------|
| `$ git branch -a` | Show all branches. |
| `$ git checkout -b <new_branch_name>` |Create new branch out of current branch and switch to new branch. |
| `$ git checkout -b <branch_name>`	| Create new branch out of current branch from particular commit and switch to new branch. |
| `$ git push <remote_name> <branch_name>` | Push local branch to remote. |
| `$ git checkout <branch_name>` | Switch to specified branch. |
| `$ git branch -d <branch_name>` | Delete local branch (replace -d by -D for force delete) |
| `$ git push <remote_name> :<branch_name>` |Delete remote branch. |

### Git stash:
##### Save current changes without commiting before doing pull and checkout to other branch
###### Run following command after `git add <file>` 
| Command | Description |
|---------|-------------|
| `$ git stash save "message"` | save chages with give message |
| `$ git stash list` | show list of stash |
| `$ git stash apply stash@{n}` | apply stashed file to current branch without deleting from stash, where `n` is the stash number |
| `$ git stash pop` | apply last stash to current branch and delete stash |
| `$ git stash clear` | clear all stash |

### Commits in git:
| Command | Description |
|---------|-------------|
| `$ git commit --amend` | Edit last commit message. |
| `$ git revert <commit_id>` | Rollback to the commit specified by commit_id |
| `$ git rebase -i HEAD~n` | Select n number of commits, it opens list of commits replace pick by reword to change the commit message of that commit. |
| `$ git reset --soft HEAD~n`	| Uncommit last n commits without overwriting the working directory files. |
| `$ git reset --hard HEAD~n`	| uncommit last n changes and overwrite the working directory files |
| `$ git cherry-pick <commit_id>` | pull commit from any branch by its commit id into current branch |

### Merging in git :
| Command | Description |
|---------|-------------|
| `$ git merge <branch_name>` | Merge any branch into current branch (creates merge commit) |
| `$ git merge <branch-name> --no-commit` | Merge without any commit. |
| `$ git pull <remote_name> <branch_name>` | pull remote branch into local branch. On conflicts it will create merege commit |
| `$ git checkout <branch_name> -- <file_name>` | checkout single file from any branch |

### Fix diverged branches:
| Command |
|:-------:|
| `git rebase <remote_name>/<branch_name>` |
| or |
| `git rebase` |

### Upstream in git :
##### Upstream is used when we have multiple repositories for single project
| Command | Description |
|---------|-------------|
| `$ git branch --set-upstream-to=<remote_name>/<branch_name> <branch_name>` | Set new upstream for the branch. |
| `$ git push -u <remote_name> <branch_name>` | push to remote branch and set as upstream |

### List commits in git (log):
| Command | Description |
|---------|-------------|
| `$ git log` | List all commits. |
| `$ git log -n` | The n is number of commits to list |

