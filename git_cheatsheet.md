Git Cheatsheet
==============

# Create a repo
git init

# List the changes
git status

# Add a single change to the staging area
git add <file_name>

# Add all changes in the current directory to the staging area
git add .

# Remove an item from the staging area
git rm <file_name> --cached
# or
git reset <file_name>

# Remove all files in the current directory from the staging area
git rm -r . --cached
# or 
git reset .


Logs
----
# View previous commits
git log
# View previous commits in a more compact formatr
git log --oneline


Revert changes
--------------
# Find the commit hash of the change you want to revert
git log 

Example:
	marfu@DESKTOP-93BU5F1 MINGW64 ~/git/git-test (master)
	$ git log --oneline
	8bd9302 (HEAD -> master) Initial commit
	a23d56d Revert "Added hello message"
	3c5bdc9 Added hello message

# The 7-character strings at the start of each line are the commit hashes
# These uniquely represent the state after every commit you have ever made

# Now revert the changes made in that commit
git revert a23d56d


Branches
--------
# List branches 
git branch -a
# Create branch
git branch <branch_name>
# Switch to a branch
git checkout <branch_name>



Checkout a remote repo
----------------------
# The path to your repo will be displayed at the top of the project page
git clone https://path.to.repo/repo_name.git

Create a repo from scratch and link to remote
---------------------------------------------
# Initialise
git init
# Add a change
git add .
# Make a commit
git commit -m "Message"
# Link local master to remote master
git remote add origin https://github.com/Mewse/git-test.git
# Push local repo to remote
git push -u origin master