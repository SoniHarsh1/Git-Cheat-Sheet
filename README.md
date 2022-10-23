## Git CheatSheet
******
### Git Basics
1. **Version Check**
    - `git --version`
2. **Status**
   - Normal : `git status`
   - Get Short Summary : `git status --short`
     - `?? : Untracked`
     - `A : Added`
     - `M : Modified`
     - `D : Deleted`
3. **Set User Name and Email in Config**
   - Set Username : `git config user.name "Username"`
   - Set Email : `git config --user.email "EmailAddress"`
   - To make this change across all repositories user `--global` tag : `git config --global user.name "Username"`
4. **Staging**
   - Stage Changes from a Single File : `git add filename`
   - Stage all Changes : `git add -all` or `git add -A`
5. **Commit**
   - Commit Staged Changes : `git commit -m "Commit Message Describing Your Changes,"`
   - Stage all Changes and Commit : `git commit -a -m "Commit Message"`
6. **Undoing Things**
   - If you miss add some file in previous commit. Then `--amend` tag with `commit`:
     - After Wrong Commit, Add forgotten file to staging Area : `git add <missed_file>`
     - Amend the previous Commit to include `<missed_file>` too : `git commit --amend`
7. **Branch**
   - Create New Branch Based on Current Branch : `git branch <new_branch_name>`
   - Get List of Branches : `git branch`
   - Checkout to Specific Branch : `git checkout <branch_name>`
   - Create new Branch based on Current Branch and Checkout to new Branch : `git checkout -b <new_branch_name>`
8. **Log And Help**
   - Get Help For A specific Command : `git <command> -help`. *Example : *`git commit -help` 
   - Get Help For All Commands : `git help --all`
   - Get Logs : `git log`
     - To get information about the change made in eache commit use `-p` tag : `git log -p` or `git log --patch`
     - Tog get logs about limited number of commits, *eg 2* : `git log -2` 
     - To get abbreviated stats use `stat` tag : `git log --stat`
     - To get ASCII graph of branch and merges : `git log -graph`
     - To get list of modified and created file after commit Operation : `git log --name-only `
     - To limit the data to certain time period use `since` or `until` tag : `git log since==2.weeks`
     - To filter commits of specific author : `git log --author="<author name>"`
     - To filter commit having some `<somestring>` present in commit message : `git log --grep="<someword>"`
     - Git pickaxe tool, Takes `<string>` as input and shows commit that changed occurances of that `<string>`: `git log -S <string>`
     - To know Commits that changed a particular file `<file>` : `git log -- <pathtofile>` 
   - Get Status of Current Branch with respect to remote: `git status`
   - Get information about Unstaged Changes : `git diff`
   - Get information about Staged Uncommited Changes : `git diff --staged` or `git diff --cached`
   - Remove deleted files from working tree and from the index, : `git rm <filename/directory/pattern>`
     - If we want to delete staged  `-f` flag : `git rm -f <filename/directory/pattern>`
     - If we want to have file in working tree but remove from tracked file, *ie* same functionality as adding to `.gitignore` : `git rm --cached <file/directory/pattern>`
### Git and Remote Repositories
1. **Add Remote**
   - Add Remote Repo as an origin to your loca git Repo : `git remove add origin <URL>`
2. **Fetch**
   - Fetch change history of tracked remote Branch(origin in this case).Repo : `git fetch origin`
3. **Merge**
   - Merge Combines Current Branch with Given Branch (origin/main in this case) : `git merge origin/main`
4. **Pull**
   - Combine Fetch and Merge. Pull remote repo and merge it with current branch : `git pull origin`
5. **Push**
   - Push Local Commited Changes to Remote repo(origin here)/Branch : `git push origin` or `git push origin/<branch_name>`
6. **Clone**
   - Clone a remote Repo to Local, with all its logs and history of files : `git clone <url_of_remote_repo>`
7. **Configure Remote**
   - Get Information About Remote : `git remote -v`
     - `fetch` will tell you what url will be used to retrieve change in fetch and pull.
     - `push` will tell you what url your local changes will be pushed to.
   - Rename remote from one to another. : `git remote rename <remote1> <remote2>`
   - Add Remote : `git remote add <remotename> <remoteurl>`
8. **UnDo**
   - To Unstage a staged file : `git reset HEAD <filename>`
   - To UnModify a Modified File : `git checkout --  <filename>`
