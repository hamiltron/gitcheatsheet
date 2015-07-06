# gitcheatsheet
My cheat sheet for handy github operations

## The usual commit routine
1. `git status` - Make sure only the intended files were modified or added. Edit the *.gitignore* file if files new files are showing up that should only be local. 
2. `git add -A` - Stage all updates to the repo. 
3. `git status` - Double-check which files are being updated/added/deleted. 
4. `git commit` 
5. `git push` - Send it into the aether for safe keeping. 

## Other basics
* `git branch` - Dispay all the local branches with the currently checked-out branch highlighted. 
* `git checkout -b [branch name]` - Create a new branch with the given name and switch to it. 
* `git checkout [branch name]` - Switch to an existing branch.
* `git branch -d [branch name]` - Delete a local branch. 
* `git push origin --delete [branch name]` - Delete a branch off the remote to reduce repo clutter. 
* `git pull` - (Really a combination of `git fetch` and `git merge`.) Pull and merge recent changes (that other people pushed to the remote) into your local copy. Be ready for conflict resolution. 
* `git log -[N]` - View the last *N* commit messages and their commit hashes. 
* `git checkout [first few 6-10 characters of commit hash]` - Go back in time by checking out a particular commit. This also works with tag names (among others). 
* `git reset` - Un-stage everything (after `git add`). Modified files will still be there. 
* `git reset --hard` - Wiped all (tracked) modifications to the currnt local branch. This makes things go POOF - be warned!

## "Oops, I modified a file on the wrong branch."
No worries. If you haven't staged anything, just checkout to a new or existing branch. 
The modified files will move with you, leaving the other branch clean (usually). If you
have staged modifications, use `git reset` to un-stage everything and then checkout a new branch. 

## Handy Config Options
* `git config --global push.default current` 
* `git config --global diff.algorithm patience` 
