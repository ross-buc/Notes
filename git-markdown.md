# Git Notes
## March 17, 2023 - 10:19 AM
- **git push -u origin main** - *updating the repository on github with changes committed in git*
- **git commit -m "example"** - *updates staged changes with the message "example"*
- **touch example.txt** - *will create a txt file called "example" in the current location*
- **mkdir example/** - *will create a folder called "example" in the current location*
- **rm example.txt** - *will delete a txt file called "example"*
- **rmdir example** - *will delete a folder called "example"*
- **git remote set-url <remote_name> <remote_url>** - *this is how you change the github remote url if you have changed the repo name*
- **git remote -v** - *this is how you check the current url connection*
- **git add "example.txt"** - *this is how you stage a file before committing*

## March 19, 2023 - 07:08 AM
- **git branch example** - *create a new branch called "example"*
- **git switch example** - *switch from the current branch to "example" branch*
- **git switch -c example** - *create and switch to a branch called "example"*
- **git status** - *shows the current status of the repo, and lets you know if there is anything edited or waiting to be committed*
- **git branch -d example** - *this will delete the branch "example"*
- **git branch -M main** - *changes the name of the master branch to main*
- **git merge example** -*if you are on the main branch, this will merge the example branch into the main branch*
## March 24, 2023 - 08:50 AM
- **git diff** - *command to view current unstaged changes between commits, branches, files and working directory*
- **git diff HEAD** - *shows all changes staged and unstaged since head.*
- **git diff --staged** - *only shows staged changes*
- **git diff --cached** - *same as git diff staged*
- **git diff --staged example.txt** - *will only show changes in the staged file called example.txt*
- **git diff main..example** - *will compare main branch and example branch*
- **git diff 4are6td..2rddr343f** -*will compare the changes between two commits using the hashes*
- **git log** - *shows the current branch commit history*
- **git log --oneline** - *shows a neat one line print of the git log history*
## March 25, 2023 - 06:21 AM
- **git clone https://github.com/Ross/example** -*This is a way of downloading a git repository from github to work on*
## April 01, 2023 - 08:32 AM
- **git stash** -*a way of stashing uncommitted changes without having to make unnecessary commits*
- **git stash pop** -*will bring the changes that were in the stash back into the working directory*
- **git stash apply** -*you can apply any changes that are in the stash without removing the files from the stash. This means you can apply stashed changes to multiple branches.*
- **git stash list** -*a way of looking at the current stash list*
- **git stash apply@{2}** -*this will apply the stash file at git stash {2} to the current directory* 
- **git stash drop stash@{2}** -*this will remove stash@{2} file from the stash list*
- **git stash clear** -*this will remove all stash files from the stash list*


