# Git branch
## working with git branches
a branch in git is a new/separate version of the main repo

## why you need a git branch
to create a separate version of the main repo and work on it independently without interfering with the main repo.

## creating a branch
```bash
git branch error_fix    # creates a new branch
git branch      # confirm that we have created a new branch
                # the asterisk on the branch indicates the current branch you are in.
git checkout branch_name    # moves us into the specified branch
```
after `git checkout branch_name` you are now able to work on the new branch without interfering with the contents of the main repo. Create new files, modify files ... and run ` git status' to see tracked and untracked changes.
NB: using -b option on checkout will create a new branch and move to it, if it does not exist
```bash
git checkout -b branch_name
```

## switching between branches
let's see how easy it is to move from branch to branch
```bash
git checkout master     # move into the main branch
git checkout -b branch_name     # move into the branch if it does not exist create and move into it
```
after working on files in the different branches stage and commit.

## git pull branch from github
if their exist a remote branch(github) 
```bash
git branch -a   # checkout the branches available both locally and remote
git branch -r   # check to see the remote branches available on remote repo
git checkout remote_branch  # change to the remote branch 
git pull    # check/pull updates
git branch  # check to see if remote repo added to branch
```

## git push branch to github
```bash
git push origin branch_name
