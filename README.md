# INTRO
- WHAT IS GIT?
    - Git is a Version Control System tool that helps to track the changes in the code.
    - It's a popular , free & open-sourc and fast & scalable

- WHAT IS GIT HUB?
    - is a website that allows developers to store and manage their code into REPOSITORY(FOLDER) using Git.

# GIT CONFIGURE & SETUP
step 1: Create Git hub account https://github.com/
step 2: Check into your sytem on cmd line weather git is intalled or not
        - git --version (If not display any version then follow step:3)
step 3: Install Required s/w
        - GIT BASH (WINDOW) : git-scm.com
        - TERMINAL (MAC)
        - VISUAL STUDIO (Can choose other editor as well)
step 2: set the user creds into your system [Set Globaly if you will be using same creds for the projects]
        git config --globally user.name "Rajesh Kumar"
        git config --globally user.email "test@gmail.com"
        git config --list [To check the configuration]

        NOTE: Prefer to use the same user name and email creds of the github account
step 3: Create Repository (Folder)

# CLONE THE REPO to you Local machine
// for ssh you have to setup the ssh key into your system, so for the beginner proceed with https
- # git clone <!--ssh url or https url of the repo -->

# GIT BASIC COMMANDS
- # git add <!-- File Name ---> // To staged the particular new /changed file

- # git add . // To staged all the new and modified file 

- # git status  // to check the status of the code
    - untracked: New files that git doesn't yet tracked.
    - modified: Changes into the existing files that git already tracked
    - staged:   Changed files ready to commit
    - unmodified: No changes in the code

- # git commit -m "<!-- meaningful commit message-->" // Commit is the record of the changes

- # git push origin main //upload local repo content to remote repo, here origin is the default repo name , main is the branch name

# Now IF you want to create your local folder as local repo and push this local repo changes to remote repo the follow the below commands
- create the a repo to your git hub account and copy the ssh/https url of the repo

// to make the your local folder as local remote, you can check if .git exist or not using ls -a command on mac 
- git init 

// to add/connet  the remote repo to local remote
- git remote add origin <!--repo ssh/https url -->
- git remote -v // to verify the the remote
- git branch // to check the current branch i.e default main
- git branch -M central // to rename the branch to central if you want

// follow the basic command to staged and commit the changes

// push the local changes commit to main branch
- git push origin main


# Branch Commands
- git branch // to check the current branch name
- git branch -M central // to rename the current branch to central 
- git checkout <!--branch-name> // navigate to the other branch
- git checkout -b <!--branch-name> // create a new branch from the current branch with same content
- git branch -d <!--branch-name> // to delete the branch [YOu have to be on other branch to delete the branch, else you can't delete the current branch]

# MERGING CODES
- If you want to merge the code of feature-branch to main-branch
- Approach-1
    - Create the PR from feature-branch to main-branch manuallly in the GIT hub

- Approach-2
    - using command lines
    - # git diff main //  to compare the commit/branches/files of the current branch i.e feature with main

    - # git merge main // merge the feature branch with main (main codes coming to feature)


# PULLING THE CODES 
- git pull origin main // used to fetch and download content from an remote repo {in this case i want to fetch and download from main to the local repo of feature branch} and immediately update the current local repo to match the content


# RESOLIVING MERGE CONFLICTS
An event that takes place when Git is unable to automatically resolves differences in code b/w two commits
- we have to resolve it manually
    - git merge main 
- after the resolving manually, commit the new changes and push
    - git commit - "message"
    - git push origin main

# UNDOING CHANGES
CASE 1: staged changes
- git reset <file-name> // undo particular file
- get reset // undo all file

CASE 2: commited changes (for 1 commit)
- git reset HEAD~1 // undo the latest commit

CASE 3: commited changes (for many commits)
find the commit-hash using: git log
- git reset <commit-hash> // undo all the commits upto that commit hash
- git reset --hard <commit-hash> // undo all the commits upto that commit hash also remove the change locally as well

