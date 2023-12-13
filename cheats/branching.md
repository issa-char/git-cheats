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

# git branch merge
merging is the joining of a branch to the main branch
to do so first move into the main/master branch
```bash
git checkout main
```
2. now merge the main branch with your branch_name
```bash
git merge branch_name
```
3. if no-conflict error delete the branch
```bash
git branch -d branch_name
```
NB: if the new branch came direclty from main and no changes had been made to main while working on the new branch no conflicts will occur, else we need to find the files causing the conflict and fix them.

## in-case of conflict during merge
```bash
git status      # check the main repo status and look for the files causing conflict
git commit -m "commit message after fixing conflict"    # concludes the merge
git branch -d branch_name   # delete the branch as it is of no use after merging to main
```

