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
- **git diff** - *command to view current changes between commits, branches, files and working directory*
- **git diff HEAD** - *shows all changes staged and unstaged since head.*
- **git diff --staged** - *only shows staged changes*
- **git diff --cached** - *same as git diff staged*
- **git diff --staged example.txt** - *will only show changes in the staged file called example.txt*
- **git diff main..example** - *will compare main branch and example branch*
- **git diff 4are6td..2rddr343f** -*will compare the changes between two commits using the hashes*
- **git log** - *shows the current branch commit history*
- **git log --oneline** - *shows a neat one line print of the git log history*
- 


