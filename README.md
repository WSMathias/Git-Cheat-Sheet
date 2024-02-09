# Git cheat sheet

| git | version >= 2.7.4 |
|-----|------------------|

### Basic git setup :


### Git config:
#### Set Global config:
##### These will be reflected as Author details in each commit you make
| Command | Description |
|---------|-------------|
| ` git config --global user.name "your_username"` | Auther |
| ` git config --global user.email "your_email"`	| Auther email |

| Command | Description |
|---------|-------------|
| ` git config --global core.editor "vim"` | Change editor to vim |
| ` git config --global core.ignorecase false`| Detect changes in filename case change |
| ` git config --global init.templatedir '~/.git_template` | Set git template dir ([to configre hooks][git-template-stackoverflow])|

#### Set Local config: ( modify config for current project)
| Command | Description |
|---------|-------------|
| ` git config  user.name "your_username"` | Auther |
| ` git config  user.email "your_email"`	| Auther email |
| ` git config core.ignorecase false`| Detect changes in filename case change |

#### Unset config:
| Command | Description |
|---------|-------------|
| ` git config --global --unset <config-key>` | Unset global config  <br>ex: git config --global --unset user.name |
| ` git config --unset <config-key>` | Unset local config  <br>ex: git config --unset user.name|

[More operations on config][git-config-stackoverflow]

### Adding git to the project:
| Command | Description |
|---------|-------------|
| ` git init .` | Initialize git inside the project root directory. |
| ` git add .` | Stage all files for commit. |
| ` git commit -m "commit-message"` | Commit staged files to git. |

### Adding Remote repo to Project:
| Command | Description |
|---------|-------------|
| ` git remote add <remote_name> <remote_address>` | Add remote repository where<br>remote_name: origin,upstream etc<br> remote_address:(url) github, bitbucket etc |
| ` git remote set-url origin <remote_address>` | Update remote address |
| ` git remote rename origin upstream`| Rename remote from origin to upstream |
| ` git remote remove <remote_name>` |	Delete remote |
| ` git remote rename origin upstream` | Rename remote |
| ` git push <remote_name> <branch-name>` | Push all the commits to remote default branch name master |

### Synchronizing local with remote (upstream):
| Command | Description |
|---------|-------------|
| ` git fetch` | Download changes from remote without making any changes to files in the working directory. |
| ` git pull` | Download remote commits from the origin repository configured as upstream for the current branch. |
| ` git push` | Upload local commits to remote. |

### Branches in git:
| Command | Description |
|---------|-------------|
| ` git branch -a` | Show all branches. |
| ` git branch <new_branch_name> ` | Create a new branch (Will not switch working tree to new branch). |
| ` git checkout -b <new_branch_name>` | Create a new branch out of the current branch and switch to the new branch. |
| ` git checkout --orphan <new_branch_name>` | Create a new branch without any parent commit (empty branch) |
| ` git branch -m <old_branch_name> <new_branch_name>` | Rename branch. |
| ` git push <remote_name> <branch_name>` | Push local branch to remote. |
| ` git checkout <branch_name>` | Switch to specified branch. |
| ` git branch -d <branch_name>` | Delete local branch (replace -d by -D for force delete) |
| ` git push <remote_name> :<branch_name>` |Delete remote branch. |
| ` git branch --contains  <commit_id>` | Search branches containing the given commit id |

### Git stash:
##### Save current changes without committing before doing pull and checkout to another branch
| Command | Description |
|---------|-------------|
| ` git stash save "message"` | Save changes with give message after running `git add <path>` |
| ` git stash list` | Show stash list |
| ` git stash pop` | Apply the last stash to the current branch and delete stash |
| ` git stash apply stash@{n}` | Apply `n`th stash without deleting from stash |
| ` git checkout stash@{n} -- <filename>` | check out a file from `n`th stash |
| ` git stash clear` | Clear all stash |
| ` git stash show -p` | view last stash content |
| ` git stash show -p stash@{n}` | view `n`th stash content |

### Commits in git:
| Command | Description |
|---------|-------------|
| ` git commit --amend` | Edit last commit message. |
| ` git revert <commit_id>` | Rollback to the commit specified by commit_id |
| ` git rebase -i HEAD~n` | Opens list of the last n commits,<br>replace _"pick"_ by _"reword"_ to alter the commit message of those commits. |
| ` git reset --soft HEAD~n`	| Uncommit the last n commits without overwriting the working directory files. |
| ` git reset --hard HEAD~n`	| Uncommit last n changes and overwrite the working directory files |
| ` git cherry-pick <commit_id>` | Pull commit from any branch by its commit id into the current branch |
| ` git rev-parse --short HEAD` | Print last commit id |
| ` git commit --all --amend --no-edit`  | Add current changes to last commit |
| ` git merge-base <branch a> <branch b>` | Get the latest common commit id between branch a and branch b |
- [Altering old commit content](https://stackoverflow.com/a/2719636)

### Merging in git :
| Command | Description |
|---------|-------------|
| ` git merge <branch_name>` | Merge any branch into current branch |
| ` git merge <branch-name> --no-commit` | Merge without merge commit. |
| ` git pull <remote_name> <branch_name>` | Pull from remote branch and merge |
| ` git checkout <branch_name> -- <file_name>` | Checkout single file from any branch |
| ` git checkout <branch_name> -- .` | Checkout all the files from any branch |

### Fix diverged branches:
| Command |
|:-------:|
| `git rebase` | Rebase on default upstrem |
| or |
| `git rebase <remote_name>/<branch_name>` | Rebase on non-upstream remote branch |

### Caching in git :
##### Run these commands after updating gitignore, then commit the changes.
| Command | Description |
|---------|-------------|
| `git rm --cached <filename>` | Remove specific file from git cache |
| `git rm -r --cached .` | Remove all files from git cache |

### Upstream in git :
##### Upstream is used when we have multiple repositories for a single project
| Command | Description |
|---------|-------------|
| ` git branch --set-upstream-to=<remote_name>/<remote_branch_name> <local_branch_name>` | Set new upstream for the branch. |
| ` git branch --set-upstream-to=<remote_name>/<remote_branch_name>` | Set new upstream for the current branch. |
| ` git push -u <remote_name> <branch_name>` | Push to remote branch and set as upstream |

### List commits in git (log):
| Command | Description |
|---------|-------------|
| ` git log` | List all commits. |
| ` git log -n` | The n is number of commits to list |
| ` git log --all --grep='<message content>'` | List/Find commits by message content |
| ` git log master..newBranch` | List commits that `newBranch` has but `master` doesn't | 


### Git diff
Note: ref1 and ref2 could be branch names, remotename/branchname, commit SHAs, etc
| Command | Description |
|---------|-------------|
| ` git diff ref1:path/to/file1 ref2:path/to/file2 ` | Show difference between two references |
| ` git diff -- path/to/file ... origin ` | Show file difference between the local file and remote file of the current branch |
| ` git diff branch_name:path/to/file ` | Simplified version of the above command |

### Git patch
without author info:
| Command | Description |
|---------|-------------|
| ` git diff > my_chnages.patch ` | Create patch file |
| ` git apply  my_chnages.patch` | Applying patch file |

### List file activity since the last commit:
| Command | Description |
|---------|-------------|
| ` git status` | List all create/modified/deleted/staged files |
| ` git status . -- ':!dir1' ':!dir2'` | skip status result for the given directories |

### Managing files:
| Command | Description |
|---------|-------------|
| ` git ls-files --others --exclude-standard` | List all untracked files. |
| ` git ls-files --modified --exclude-standard` | List all modified files. |
| ` git update-index --assume-unchanged <ignore file>` | Ignore file modification. |
| ` git update-index --no-assume-unchanged <ignored file>` | Revert above action. |
| `git show <branch>:<file>` | Peek into file from diffrent branch. |

### Git worktree:
Useful when working on multiple branches locally at the same time  without maintaining multiple clones for each branch.
| Command | Description |
|---------|-------------|
| ` git worktree add ../myProject-master master` | Master branch code can be accessed at `../myProject-master` |
| ` git worktree list` | list all worktrees from project directory |
| ` git worktree remove ../myProject-master` | Delete worktree (folder will still be there) |
| ` git worktree repair ../new/worktree/path` | Repair worktree after moving worktree or bare repository locally to a different location|

### Git Submodule:
Commands to manage submodules.
| Command | Description |
|---------|-------------|
| ` git submodule add <repo_address> <submodule_path>` | Add new submodule at submodule_path |
| ` git submodule update --init` | Download all the submodules after cloning the main repo and also resets the submodule commit to the parent commit |

### Git Restore:
Commands to copy the directory.
| Command | Description |
|---------|-------------|
| ` git restore --source <branch>  dirname ` | Copy the directory from any branch without git history |

### Git repo maintenance
Commands keep the local repo clean and faster.
| Command | Description |
|---------|-------------|
| ` git prune ` | Clean up orphaned objects/commits |


### Time savers
##### Edit the last commit which is already pushed to remote.  
` git add . && git commit --amend --no-edit && git push --force`

#### Merge multiple local commits into a single commit before pushing to remote
` git rebase -i HEAD~10`  
replace `pick` by `fixup` for the commits you want to merge.  
##### Note: Oldest commit is at the top.

### Tips:
#### Disable terminal screen (oh-my-zsh)
Add the below line to `~/.zshrc` for permanent change.
```bash
unset LESS
```

### Reference:
---
- [http://schacon.github.io/git/git.html](http://schacon.github.io/git/git.html)  
- [zsh git aliases](https://github.com/ohmyzsh/ohmyzsh/wiki/Cheatsheet#git)
- [What is HEAD ?](https://stackoverflow.com/a/54935492/7247089)
- [git-internals-pdf](https://github.com/pluralsight/git-internals-pdf)

[git-template-stackoverflow]: https://stackoverflow.com/questions/2293498/applying-a-git-post-commit-hook-to-all-current-and-future-repos
[git-config-stackoverflow]: https://stackoverflow.com/questions/11868447/how-can-i-remove-an-entry-in-global-configuration-with-git-config


