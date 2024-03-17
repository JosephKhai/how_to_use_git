# how_to_use_git_at_your_work_place

First you need to install git in your local machine: 
- https://git-scm.com/book/en/v2/Getting-Started-Installing-Git

#configure email and username
- git config --global user.email "your-email@example.com"
- git config --global user.name "Your Name"


#Clone from Existing github
- Create a new folder where you want to save on your local machine. eg. C:\dev
- open dev folder > right click in the folder and select 'open in terminal' or run command prompt and open your folder. 
- type 'git clone <pastse_url_of_git_repo>'


#Merge your branch to Master branch - safe way to do
- Before you begin to merge
  commit your work first or git stash
- git add *
- git commit -am "name of commit"
- git push
- or
- git stash (save somewhere your work)
- after merging your branch
- git stash pop (call it it back your work)

What is git stash?
- takes your uncommitted changes (both staged and unstaged), saves them away for later use

- what is `-am` stand for?
-a: This flag stands for "all" and tells Git to automatically stage all modified files before committing them. It's equivalent to running git add -u to stage all modified and deleted files.
-m: This flag stands for "message" and is followed by the commit message enclosed in quotes. It allows you to specify the commit message directly from the command line. Without this flag, Git would open your default text editor for you to enter the commit message.
When you use git commit -am "Your commit message", Git stages all modified files (excluding untracked files) and commits them with the specified commit message, all in one command.
  
///Start merging
- git fetch (from your local branch - update your local branch) 
- git rebase origin/master (from your local branch - get some update from master to your branch incase other developer push or update in the master branch)
- If you have conflict, fix them carefully and continue until all is fix
- git checkout master (switch to master branch)
- git pull origin master (get update to your local master branch from remote master branch)
- git merge/rebase <your_branch_name> (finally merge your branch to master - you can use either 'merge' or 'rebase' keyword. 'rebase' keyword is recommended)
- If you have conflict, fix them carefully and continue until all is fix
- git push origin master


#update your git branch from Master branch
- Step 1. git checkout master (switch to master branch)
- Step 2. git pull (to update your local master from remote master)
- Step 3. git checkout <your_branch> (switch it back to your branch)
- Step 4. git merge master or git rebase master (merge master branch to your branch)
- And then solve all merge conflicts if you have
- git rebase --continue
- git push 


#Create a new Branch from Master
- git checkout -b <new_branch_name>
- git push

#Merge feature_b branch to feature_a branch (branch to branch merging)
-git checkout feature_b
- git pull (get remote feacture_b changes to your local machine)
- git checkout feature_a (switch it back to your branch)
- git merge feature_b (merge feature_b to your branch feature_a)

Note: you can use Github Desktop or Visual Studio or Visual Studio Code interface. However I feel a bit easier solving merge conflict in the terminal.

- Reference: https://www.atlassian.com/git
- Practice git at: https://learngitbranching.js.org/


