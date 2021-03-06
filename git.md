# Committing
## Add all changes to index
git add .

## Create a commit
git commit -m "Initial commit"

## Push to origin
git push -u origin master

# Checkout
## Checkout file from most recent commit
git checkout -- filename

# Show a log of all the commits
git log

# Show who modified what and when in a file (so you can blame them!)
git blame <file>

# Branching
## Create a new branch
git branch <branch_name>

## Checkout a branch
git checkout <branch_name>

## Create a new branch and check it out
git checkout -b <branch_name>

## Delete a local branch
git branch -D <branch_name>

## Delete a remote branch
git push origin --delete <branch_name>

# Reverting Changes
## Removes directories and files (use when having discard changes errors)
git clean -df

## If git clean doesn't work, this is the next step
git rm -rf *

## Discard all changes and reset to a specific commit
git reset --hard 0d1d7fc32

## Unstage all changes
git reset --

## Unstage a specific file
git reset <file>

#Subtree
## Add a subtree without adding the entire history of the sub project via squash
(Must done at the top level of a _clean_ working directory)
git subtree add --prefix vendor_cookbooks/yum https://github.com/opscode-cookbooks/yum master --squash

## Update a subtree
git subtree pull --prefix vendor_cookbooks/yum https://github.com/opscode-cookbooks/yum master --squash

## Remove a subtree
Since the subtree is treated as a merge commit, you just remove the directory
the subtree was pulled down to like any other directory
git rm -r <subtree_dir>

#Submodules
## Add a submodule, do a git add/commit after to add it to the repo
git submodule add repo dest_dir
git submodule add https://github.com/plasticboy/vim-markdown.git bundle/vim-markdown

## Init and update a submodule after cloning
git submodule update --init

## To update a submodule, go into the local repo dir
git pull origin master

## Update all submodules
git submodule foreach git pull origin master

## Remove a submodule
git submodule deinit asubmodule
git rm asubmodule

# Stashes
## Add all the changes
git add .

## Create the stash
git stash

## And boom! You’re back to your original working state. Got that bug fixed? Bring your work back with:
git stash apply

# Deleting
## Prune remote branches that have been removed from the local db
git remote prune origin
