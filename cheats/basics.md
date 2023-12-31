# Git and Github Introduction
git is a popular version control system.
It is used for:
    * tracking code changes
    * tracking who made changes
    * coding collaboration

# capabilites of git
    * manage projects with repo
    * `clone` a project to work on a local copy
    * control and track changes with staging and commiting
    * `branch` and `merge` to allow for work on different parts and versions of a project
    * `pull` the latest changes to upstream project
    * `push` local updates to main repo

## to work with git
    * install git
    ```bash
    sudo apt install git
    ```
    * confirm version
    ``bash
    git --version
    ```
# step ONE 
## create a github repo
1. head over to github and set an account
2. login and create a new repository with (follow the listed instructions that suits your needs)
3. go to setting and set-up tokenized authentication and save the token locally
4. copy the repo link you've just created

# step two
## configure git
after successful installation, we need to configure git to know who you are.
this is important as each commit will use this information and probably should match with your github credentials.
```bash
git config --global user.name "your_user_name"
git config --global user.email "your_email"
```

the --gloabl option sets git system wide. To only configure the username and email on a specific directory remove the global.
``` bash
    git config user.name "your_user_name"
    git config user.email "your_email"
```
# step THREE
## create a directory
``` bash
    mkdir your_project_directory
    cd your_project_directory
```
mkdir creates your directory while cd changes into the directory

# step FOUR
## initialize git on the project directory
```bash
    git init
    git remote add origin <the_url_to_your_github_repo> # specifies that you are adding a remote repo(url) as an origin to your local repo.
```
your successfully created your first git repo, congratulations!
git creates a directory (.git) to keep track of all changes made in that directory.
this directory is how git knows all about your repo. If deleted, the directory is no longer a git repo.

# step FIVE
## adding new files
create new files using your favourite text editor or add exsting ones to the initialized dir.
```bash
ls    # list the files in your dir
git status    # check if the files are part of repo
git add file1 file2   # choose the files you want to add/track in  the repo
git add *     # place all modified files in the staging envrionment/track
git add --all     # same as above
git status    # check on the state of your repo
```
you successfully added new files to your git repo.
files in your repo can be in two states: `tracked`and `untracked`.
tracked are files that git know about and are added to the repo
untracked are files in your dir but not added to the repo.
untracked files are added to the repo to be tracked.
tracked files are placed in a staging environment waiting to be approved/commited.

# step SIX
## commiting tracked files/files in the staging environment
adding commits keep track of all our progress and changes.
when we commit we include a message: clear and an easy to understand to see what changed and when.
by commiting we are able to go come back to this stage, if we encounter a bug/issue.
```bash
$ git commit -m "your commmit message" # commit your tracked files/changes
$ git commit -a -m "your commit message"  # an alternative to skip the 'track/add' stage
$ git status --short    # check on repo state in a more compact way
```
# step SEVEN
## pushing your changes to github
this will publish our repo on github
```bash
git push --set-upstream origin master/main
```
log into github and see that the repo as been uploaded

## commit log
commit log are the history of your commits for the repo
```bash
$ git log   # view your commit logs
```
# step SEVEN
## getting help
if you ever get stack on a command or need to know some git options use the following help command
```bash
$ git {command} -help   # see all the available options for the specific command
$ git help --all    # see all possible commands
```

# step EIGHT
## git pull from github
git push is to publish to github while `git pull` is to get the upstream changes to your local copy; sync github repo copy to your local copy, that is if you made changes to the upstream copy and not locally.

```bash
git pull origin
```
### git pull but longer/detailed
1. fetch updates from repo
```bash
git fetch origin
```
2. check status to see what if we behind or ahead of github repo
3. verify by checking the updated logs
```bash
git log origin/master
git diff origin/master  # shows the difference between the upstream repo and local repo
```
4. merge local branch with origin/master(upstream)
```bash
git merge origin/master # updates your local repo to reflect the upstream repo
```
now your local repo is up to date.


