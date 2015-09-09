# Git Cheat Sheet
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
* `git merge [branch name]` - Merge the named branch with the currently checked-out branch, automatically committing the results. 
* `git branch -d [branch name]` - Delete a local branch. 
* `git push -u` - Push a new local branch to the remote and set upstream tracking so pulls automatically work too. Note: this ONLY works if *push.default* is set to *current*, otherwise you have to use the standard longer form of the command.  
* `git push origin --delete [branch name]` - Delete a branch off the remote to reduce repo clutter. 
* `git pull` - (Really a combination of `git fetch` and `git merge`) Pull and merge recent changes (that other people pushed to the remote) into your local copy. Be ready for conflict resolution. 
* `git log -[N]` - View the last *N* commit messages and their commit hashes. 
* `git checkout [hash prefix]` - Go back in time by checking out a particular commit. This also works with tag names (among other identifiers). 
* `git checkout [hash prefix] [file path]` - Grab a file from a particular commit to get a past version of it.
* `git reset` - Un-stage everything (due to `git add`). Modified files will still be there. 
* `git reset --hard` - Wiped all (tracked) modifications to the current local branch. **POOF WARNING!** 
* `git reset --hard [hash prefix]` - Roll back the repo to a particular commit. **POOF WARNING!** 
* `git clean -fdx` - Delete all non-repository files (as if you'd just cloned it). **POOF WARNING!** 

*POOF WARNING*: commands that make files go 'POOF' - as in you can't get them back

*hash prefix*: first six to ten characters of commit hash

## "Oops, I modified a file on the wrong branch."
No worries. If you haven't staged anything, just checkout to a new or existing branch. 
The modified files will move with you, leaving the other branch clean (usually). If you
have staged modifications, use `git reset` to un-stage everything and then checkout a new branch. 

## Handy Config Options
* `git config --global push.default current` 
* `git config --global diff.algorithm patience` 
* `git config --global core.mergeoptions --no-edit`
* `git config --global merge.ff false`
