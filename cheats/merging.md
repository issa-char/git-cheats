
# git branch merge
merging is the joining of a branch to the main branch
to do so:

1. first move into the main/master branch
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

NB: if the new branch came direclty from main and no changes had been made to main while working on the new bran    ch no conflicts will occur, else we need to find the files causing the conflict and fix them.

## in-case of conflict during merge
```bash
git status      # check the main repo status and look for the files causing conflict
git commit -m "commit message after fixing conflict"    # concludes the merge
git branch -d branch_name   # delete the branch as it is of no use after merging to main
 ```

