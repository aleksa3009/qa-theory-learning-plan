# Git & GitHub Commands 

## Repository & Initialization
- `git init` - create a new local repository
- `git clone <url>` - copy a remote repository locally
- `git remote -v` - show configured remote repositories
- `git branch` - list branches
- `git branch <name>` - create a new branch
- `git checkout <branch>` / `git switch <branch>` - switch to a branch
- `git checkout -b <branch>` / `git switch -c <branch>` - create & switch to a branch

## Staging & Committing
- `git status` / `git status -s` - view current changes
- `git add <file>` - stage file for commit
- `git add .` - stage all changes
- `git commit -m "message"` - commit staged changes with a message
- `git commit -am "message"` - stage & commit tracked files
- `git diff` - show unstaged changes
- `git diff --staged` - show staged changes

## Branching & Merging
- `git merge <branch>` - merge a branch into current branch
- `git rebase <branch>` - reapply commits on top of another branch
- `git log --oneline --graph --all` - visualize branch history

## Remote Operations
- `git fetch` - download remote changes without merging
- `git pull` - fetch and merge remote changes
- `git push` - push local commits to remote
- `git push -u origin <branch>` - push and set upstream

## Undoing & Restoring Changes
- `git reset <file>` - unstage a file
- `git restore <file>` - discard local changes
- `git restore --staged <file>` - unstage a file
- `git checkout -- <file>` - revert file to last commit (destructive)
- `git restore --source <commit> <file>` - restore file from specific commit
- `git reset --soft <commit>` - move branch pointer, keep changes staged
- `git reset --hard <commit>` - reset branch and working directory (destructive)

## Removing, Moving & Renaming Files
- `git rm <file>` - remove file from repo & working directory
- `git rm --cached <file>` - remove file from repo, keep locally
- `git mv <old> <new>` - rename/move file
- `rm -rf <folder>` - force delete folder & contents (CLI)

## Tags & Releases
- `git tag <name>` - create a tag
- `git push --tags` - push tags to remote

## Stashing & Temporary Work
- `git stash` - save uncommitted changes
- `git stash pop` - apply and remove stash

## History & Inspection
- `git log` - show commit history
- `git log --oneline` - compact view
- `git log -- <file>` - history for a file
- `git show <commit>` - view specific commit
- `git ls-tree HEAD` - list contents of a commit/tree
- `git blame <file>` - see line-by-line commit info
- `git bisect` - binary search to find bug-introducing commit
- `git reflog` - log of HEAD changes

## GitHub Specific (CLI)
- `gh repo clone owner/repo` - clone via GitHub CLI
- `gh pr create` - create a Pull Request
- `gh pr review` - review a Pull Request