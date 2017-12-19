<h1>Git cheat sheet</h1>
<table>
	<tr>
		<td>
		git version 2.7.4
		</td>
	</tr>
</table>

<h2>Basic git setup :</h2>
<table>
	<tr>
		<th> Command </th>
		<th> Description </th>
	<tr>
	<tr>	
		<td >
			$ git config --global user.name "your_username" <br>
			$ git config --global user.email "your_email"
		</td>
		<td>
			These will be reflected as <b>Author</b> details in each commit you make.
		</td>
	</tr>
</table>

<h2>Adding git VCS to project : </h2>
<table>
	<tr>
		<th> Command </th>
		<th> Description </th>
	<tr>
	<tr>
		<td>
			$ git init .
		</td>
		<td>
			Initialize git inside project root directory.
		</td>
	</tr>
	<tr>
		<td>
			$ git add .
		</td>
		<td>
			Stage all files for commit.
		</td>
	</tr>
	<tr>
		<td>
			$ git commit -m "commit-message"
		</td>
		<td>
			Commit staged files to git.
		</td>
	</tr>
	</table>
	<table>
	<h2>Adding Remote repo to Project : </h2>
	<tr>
		<th> Command </th>
		<th> Description </th>
	<tr>
	<tr>
		<td>
			$ git remote add <-remote_name-> <-remote_address->
		</td>
		<td>
			add remote repository where<br>
			remote_name: origin,upstream etc<br>
			remote_address:(url) gethub, bitbucket etc	
		</td>
	</tr>
	<tr>
		<td>
			$ git remote remove <-remote_name->
		</td>
		<td>
			delete remote	
		</td>
	</tr>
	<tr>
		<td>
			$ git push <-remote_name-> <-branch-name->
		</td>
		<td>
			push all the commits to remote <br>
			default branch name master
		</td>
	</tr>
</table>
<table>
<h2>Synchronizing local git with remote (upstream) :</h2>
	<tr>
		<th> Command </th>
		<th> Description </th>
	</tr>
	<tr>
		<td>
			$ git fetch
		</td>
		<td>
			Download changes from remote without making any changes to files in the working directory.
		</td>
	</tr>
	<tr>
		<td>
			$ git pull
		</td><td> 
			Download others commits from remote and apply to working directory.
		</td>
	</tr>
	<tr>
		<td>
			$ git push
		</td>
		<td>
			Upload local commits to remote.
		</td>
	</tr>
</table>
<table>
<h2>Branches in git:<h2>
	<tr>
		<th> Command </th>
		<th> Description </th>
	<tr>
		<td>
			$ git branch -a
		</td>
		<td>
			Show all branches.
		</td>
	<tr>
	<tr>
		<td>
			$ git checkout -b <-new_branch_name-> 
		</td>
		<td>
			Create new branch out of current branch and switch to new branch.
		</td>
	</tr>
	<tr>
		<td>
			$ git checkout -b <branch_name> <commit_id> 
		</td>
		<td>
			Create new branch out of current branch<br> from particular commit and switch to new branch.
		<td>
	</tr>
	<tr>
		<td>
			$ git push <-remote_name-> <-branch_name->
		</td>
		<td>
			Push local branch to remote.
		</td>
	</tr>
	<tr>
		<td>
			$ git checkout <-branch_name->
		</td>
		<td>
			Switch to specified branch.
		</td>
	</tr>
	<tr>
		<td>
			$ git branch -d <-branch_name->
		</td>
		<td>
			Delete local branch (replace -d by -D for force delete)
		</td>
	</tr>
	<tr>
		<td>
			$ git push <-remote_name-> :<-branch_name->
		</td>
		<td>
			Delete remote branch.
		</td>
	</tr>
</table>
<table>
<h2>Commits in git :<h2>
	<tr>
		<th> Command </th>
		<th> Description </th>
	<tr>
	<tr>
		<td>
			$ git commit  --amend
		</td>
		<td>
			Edit last commit message.
		</td>
	</tr>
	<tr>
		<td>
			$ git revert <-commit_id->
		</td>
		<td>
			Rollback to the commit specified by <b>commit_id</b>
		</td>
	</tr>
	<tr>
		<td>
			$ git rebase -i HEAD~n
		</td>
		<td>
			Select <b>n</b> number of commits, it opens list of commits<br> replace <b>pick</b> by <b>reword</b> to change the commit message of that commit. 
		</td>
	</tr>
	<tr>
		<td>
			$ git reset --soft HEAD~n
		</td>
		<td>
			Uncommit last <b>n</b> commits without overwriting the working directory files.
		</td>
	</tr>
	<tr>
		<td>
			$ git reset --hard HEAD~n
		</td>
		<td>
			uncommit last n changes and overwrite the working directory files
		</td>
	</tr>
</table>
<table>
<h2>Merging in git : </h2>
	<tr>
		<th> Command </th>
		<th> Description </th>
	</tr>
	<tr>
		<td>
			$ git merge <-branch_name->
		</td>
		<td>
			Merge any branch into current branch (creates merge commit)
		</td>
	</tr>
	<tr>
		<td>
			$ git merge <-branch-name->  --no-commit
		</td>
		<td>
			Merge without any commit.
		</td>
	</tr>
	<tr>
		<td>
			$ git pull <-remote_name-> <-branch_name->
		</td>
		<td>
			Merge remote branch into local branch.
		</td>
	</tr>
</table>
<table>
<h2>Upstream in git : </h2>
<p> Upstream is used when we have multiple repositories for single project</p>
	<tr>
		<th> Command </th>
		<th> Description </th>
	</tr>
	<tr>
		<td>
			$ git branch --set-upstream-to=<-remote_name->/<-branch_name-> <-branch_name->
		</td>
		<td>
			Set new upstream for the branch.
		</td>
	</tr>
</table>
<table>
<h2> list commits in git (log):<h2>
	<tr>
		<th> Command </th>
		<th> Description </th>
	</tr>
	<tr>
		<td>
			$ git log
		</td>
		<td>
			List all commits.
		</td>
	</tr>
	<tr>
		<td>
			$ git log -<-limit->
		</td>
		<td>
			The <b>limit</b> is number of commits to list
		</td>
	</tr>
</table>