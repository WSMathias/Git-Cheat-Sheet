<h1>Git cheat sheet for everyone <h1>
<h2>Basic git setup :</h2>
<table>
	<tr>
		<th> command </th>
		<th> description </th>
	<tr>
	<tr>	
		<td >
			$ git config --global user.name "your_username" <br>
			$ git config --global user.email "your_email"
		</td>
		<td>
			these details will be reflected in each commit you make.
		</td>
	</tr>
</table>

<h2>Adding git VCS to project : </h2>
<table>
	<tr>
		<th> command </th>
		<th> description </th>
	<tr>
	<tr>
		<td>
			$ git init .
		</td>
		<td>
			initialize git inside project root directory
		</td>
	</tr>
	<tr>
		<td>
			$ git add .
		</td>
		<td>
			stage all files for commit
		</td>
	</tr>
	<tr>
		<td>
			$ git commit -m "commit-message"
		</td>
		<td>
			commit staged files to git
		</td>
	</tr>
	</table>
	<table>
	<h2>Adding Remote repo to Project : </h2>
	<tr>
		<th> command </th>
		<th> description </th>
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
		<th> command </th>
		<th> description </th>
	</tr>
	<tr>
		<td>
			$ git fetch
		</td>
		<td>
			fetch changes from remote.
			(no changes are made to local)
		</td>
	</tr>
	<tr>
		<td>
			$ git pull
		</td><td> 
			pull others commits from remote (updates working directory)
		</td>
	</tr>
	<tr>
		<td>
			$ git push
		</td>
		<td>
			upload new commits to remote 
		</td>
	</tr>
</table>
<table>
<h2>Branches in git:<h2>
	<tr>
		<th> command </th>
		<th> description </th>
	<tr>
		<td>
			$ git branch -a
		</td>
		<td>
			show all branches
		</td>
	<tr>
	<tr>
		<td>
			$ git checkout -b <-new_branch_name-> 
		</td>
		<td>
			create new branch out of current branch and switch to new branch
		</td>
	</tr>
	<tr>
		<td>
			$ git checkout -b <branch_name> <commit_id> 
		</td>
		<td>
			create new branch out of current branch and <br> from particular commit and switch to new branch
		<td>
	</tr>
	<tr>
		<td>
			$ git push <-remote_name-> <-branch_name->
		</td>
		<td>
			to push local branch to remote
		</td>
	</tr>
	<tr>
		<td>
			$ git checkout <-branch_name->
		</td>
		<td>
			switch to specified branch
		</td>
	</tr>
	<tr>
		<td>
			$ git branch -d <-branch_name->
		</td>
		<td>
			delete local branch (replace -d by -D for force delete)
		</td>
	</tr>
	<tr>
		<td>
			$ git push <-remote_name-> :<-branch_namr->
		</td>
		<td>
			delete remote branch
		</td>
	</tr>
</table>
<table>
<h2>Commits in git :<h2>
	<tr>
		<th> command </th>
		<th> description </th>
	<tr>
	<tr>
		<td>
			$ git commit  --amend
		</td>
		<td>
			edit last commit message
		</td>
	</tr>
	<tr>
		<td>
			$ git revert <-commit_id->
		</td>
		<td>
			rollback to the commit specified by commit_id
		</td>
	</tr>
	<tr>
		<td>
			$ git rebase -i HEAD~n
		</td>
		<td>
			select n number of commits, it opens list of commits<br> replace <b>pick</b> by <b>reword</b> to change the commit message of that commit. 
		</td>
	</tr>
	<tr>
		<td>
			$ git reset --soft HEAD~n
		</td>
		<td>
			uncommit last n commits without overwriting the working directory files
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
		<th> command </th>
		<th> description </th>
	</tr>
	<tr>
		<td>
			$ git merge <-branch_name->
		</td>
		<td>
			to merge any branch into current branch (creates auto merge commit)
		</td>
	</tr>
	<tr>
		<td>
			$ git merge <-branch-name->  --no-commit
		</td>
		<td>
			merge without any commit
		</td>
	</tr>
	<tr>
		<td>
			$ git pull <-remote_name-> <-branch_name->
		</td>
		<td>
			merge remote branch into local branch
		</td>
	</tr>
</table>
<table>
<h2>Upstream in git : </h2>
<p> Upstream is used when we have multiple repositories for single project</p>
	<tr>
		<th> command </th>
		<th> description </th>
	</tr>
	<tr>
		<td>
			$ git branch --set-upstream-to=<-remote_name->/<-branch_name-> <-branch_name->
		</td>
		<td>
			set new upstream for branch
		</td>
	</tr>
</table>
<table>
<h2> list commits in git (log):<h2>
	<tr>
		<th> command </th>
		<th> description </th>
	</tr>
	<tr>
		<td>
			$ git log
		</td>
		<td>
			list all commits
		</td>
	</tr>
	<tr>
		<td>
			$ git log -<-limit->
		</td>
		<td>
			<b>limit</b> is number of commits to list
		</td>
	</tr>
</table>
