# Git Commands

- git init : initializes a git repository locally
- git add (?) : adds any file/folder to the repository
- git commit -m "message" : commits the added file/folders for final addition
- git checkout {commit hash} : attaches HEAD to the last commit
  ![](Media/Pasted%20image%2020260821145819.png)

- git status : Shows the status of commits
  ![](Media/Pasted%20image%2020260821145955.png)

- git checkout main : Attaches HEAD to main
  ![](Media/Pasted%20image%2020260821150231.png)

- git checkout -f main : Discard any changes made in detached HEAD state
- git branch -M {branch_name} : Changes current branch
- git remote add origin {repo link} : Connects local repo to remote repo
- git push -u origin main : Pushes the local repo to the remote repo
- git branch {branch_name} : Creates a new branch
- git checkout {branch_name} : Switching to any branch
- git checkout -b {branch_name} : Creates a new branch and switches to it in one go
- git branch {new_branch_name} {source_branch} : Creates a new branch inside a particular branch
- git push --set-upstream origin {branch_name} : Syncs a local branch to remote repo
- git push -u origin {branch_name} : Syncs the branch to remote repo
- git pull : Update local branch with remote branch
