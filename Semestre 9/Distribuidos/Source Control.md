**Version Control**

Tracks and manages changes
- Deletes
- Updates
- Changes
- Movements
- 
Saves metadata of the person who made the change
- Also a timestamp of the time it was changed

It allows a rollback of the previous changes in the history of the source control

>QA: Area responsible of quality of the product, makes tests

# Benefits

- Keeps a full history of the changes of a project
- Allows branching and merging. A branch is a copy of the project, which allows isolated changes. Once the changes are approved it can be merged on the main branch
- Traceability of the changes. When, where and who made the change

___
# Git

**Repository**
- Structure that contains all the files
- Saves all the changes 
- Two types:
	- Local
	- Remote

	**Commits**
	- Its a 

**Staging Area**
- Space that have changes with `git add` 

**Local Repo**
- Space that has changes that have been commited

**Remote Repo**
- Providers that give a space in the cloud
	- GitHub, GitLab

> Jira: Tracker software


Use GitBook to make documentation.
- Connect it with uni domain to get it

# Basic Commands

BASIC COMMANDS:
- git clone: clones an existing remote repo
	git clone [URL]
- git branch: displays the current branches. 
	The one we are on is marked by a *
- git branch [name]: creates a new branch
- git checkout [name]: changes from branch
- git checkout -b [name]: creates and switches to [name]
- git branch -d [name]: deletes a branch. It has to be in a different branch
	git branch -D [name]: Forces delete
	
REMOTE REPO:
1. Create remote repo in GitLab
2. Create local repo
3. Create a local commit to create a main branch
4. Sync (git push -u origin main) (We use -u origin because in the remote doesn't exist the main branch that does in local)
- git push: Only pushes the changes of the branch we're on
- git log --graph: Shows a graph of the branches
GIT FETCH
Only downloads the changes from remote repo, it doesn't apply them. We have to do a manual merge to make the changes
GIT PULL
It does a merge  in the local repo of the changes from the remote repo
- git merge [origin/branch-name]: It does a merge from the specified remote to the specified branch
	Sometimes it occurs conflicts, it has to be resolved manually 
	
MERGE
Creates a temporal branch for the differences encountered until the conflicts are resolved
REBASE
- git rebase [origin/branch-name]
On the conflicts in the file, now HEAD is the remote, and the hash is the local differences
In the rebase we have to force the push to make the changes remote
The rebase maintains the history as lineal as possible. Some commits will be lost
It can cause to lose the resolved conflicts changes