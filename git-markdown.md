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
## April 17, 2023 - 05:58 AM
- **git checkout 4pd3f22** -*travel back to a previous commit. Head will now be detached from a branch reference (main). In this state you can view, copy or branch off etc*
- **git checkout HEAD~1** -*will switch head to the parent commit of the current commit you are on*
- **git checkout HEAD~2** -*will switch head to the grand-parent commit of the current commit you are on.. etc.. etc*
- **git switch -** -*will reverse the detached head state and put you back on the branch you detached from*
- **git checkout HEAD example.txt** -*if you have made changes to example.txt but not committed them yet, using this command it will remove the changes and revert back to most recent commit that HEAD is pointing to.*
- **git checkout -- example.txt** -*same as above*
- **git restore example.txt** -*will restore example.txt back to what it was at HEAD state*
- **git restore --source HEAD~1 example.txt** -*This will restore the example.txt back to the parent commit of current HEAD, you can also put a commit hash as the source*
- **git reset 2eP902E** -*will reset the repo back to the 2eP902E commit, but the changes will still be in the file as unstaged*
- **git reset --hard 2eP902E** -*will reset the repo back the commit and the changes will be removed completely*
- **git revert 2eP902E** -*creates a new commit without 2eP902E commit changes*
## May 26, 2023 - 08:51 AM
- **git remote -v** -*This will display a list of remotes for the repository* 
- **git remote add \<name> \<url>** -*This is how you set up the remote for a repository. Usually the remote name is origin*
- **git push \<remote> \<branch>** -*This will upload the specified branch to the remote url*
- **git push \<remote> \<local-branch>:\<remote-branch>** -*To push a local branch up to a specified remote branch*
- **git push -u origin main** -*Using the "-u" function sets the upstream of the local main branch so that it tracks the main branch on the origin repo. You can now just type git push when on that branch and it will automatically upload or push to the set repo branch*
## May 29, 2023 - 08:22 AM

- **origin/main** -*This is a remote tracking branch. It's like a bookmark pointing to the last known commit on the main branch on origin. Formatted like this \<remote>/\<branch>*
- Making a commit on the local main branch will move the where the head of main is pointing to but the origin/main remote reference doesn't move.
- **git checkout origin/main** -*will move your head back to where the remote repo was. You can then create a new branch and make changes if necessary or using git push origin main will update the remote to the head of local repo*
- **git branch -r** -*This command shows a list of remote branches available in the repo.*
- **git switch \<remote-branch-name>** -*will create a new local branch of the remote branch of the same name. It also will also set up tracking of the remote branch origin/example.*
### Fetching and Pulling
- **Fetching** allows you to download changes from a remote repo, but those changes will not be automatically integrated into the working files. It lets you see what others have been working on, without having to mergre those changes into your local repo.
- **git fetch \<remote>** -*This command will only fetch specific branches and history from a remote repo.* 
- **git fetch origin** -*This will fetch all changes from the origin remote repo.* 
- **Pulling** git pull updates the head branch with whatever changes are retrived from the remote.
- **git pull origin \<example-branch>** -*Is the command used to merge updates from the remote repo to the local repo. If there are conflicts, these will need to be resolved.*
- It is good practise to pull before pushing changes to remote as there may be changes already.
- **git pull** -*using git pull will have a default remote of origin and the the current workspace branch you are working on. For example, if you are working on a branch called hotfix, if you were to type git pull, it would pull down the update from origin hotfix.*
- Make sure to save any uncommited work before pulling
## June 27, 2023 - 10:50 AM
The git merge --no-ff command is used in Git to merge a branch into the current branch while avoiding a "fast-forward" merge. A fast-forward merge moves the current branch pointer to the latest commit of the merged branch if it's ahead, making it appear as though the commits were made directly on the current branch. The --no-ff option, however, forces Git to create a new commit for the merge, even if a fast-forward is possible, thereby preserving the separate history of the merged branch.

An example of a git merge with a conflict on a branch would look like this:
- git fetch origin
- git switch my-new-feature
- git merge main
- fix conflicts
- git switch main
- git merge my-new-feature
- git push origin main

