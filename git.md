# Committing
## Add all changes to index
git add .

## Create a commit
git commit -m "Initial commit"

## Create a commit with a multi-line message
git commit -a
Line 1
Line 2
EOF

## Create a commit and use $EDITOR to enter message
git commit

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
