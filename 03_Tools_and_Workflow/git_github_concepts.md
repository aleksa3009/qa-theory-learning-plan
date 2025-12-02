# Git & GitHub Concepts

## What is Git?
- Git - a distributed version control system (DVCS) that records snapshots (commits) of a project
- Supports branching and merging
- Each user has a full copy of the repository history

## Core Concepts
- Repository - project files and full history (local .git folder holds data)
- Working Directory - current checked-out files
- Staging Area (Index) - where changes are placed before committing (git add)
- Commit - an immutable snapshot with a message and metadata (author, date, parent commit(s))
- HEAD - pointer to the current commit (usually tip of current branch)
- Branch - lightweight pointer to a commit (used to isolate work)
- Remote - a named reference to another repo (e.g., origin)
- Tag - named pointer to a commit (often used for releases)

## Basic Workflows
- Initialize repo: git init
- Clone remote repo: git clone <url>
- Stage changes: git add <file>
- Commit: git commit -m "msg"
- Create/switch branch: git checkout -b <branch> / git switch -c <branch>
- Merge: git merge <branch>
- Rebase: git rebase <branch>
- Push/Pull: git push / git pull

## Branching & Merging
- Use short-lived branches for features or bug fixes
- Merge combines changes, may create merge commit
- Fast-forward merge moves branch pointer forward if no divergent history
- Rebase produces linear history; avoid on public branches

## Undoing Changes
- Unstage: git reset <file> or git restore --staged <file>
- Discard local changes: git restore <file> or git checkout -- <file> (destructive)
- Move branch pointer: git reset --soft <commit> (keep changes staged), --mixed (default), --hard (discard changes)
- Recover lost commits: git reflog then git checkout or git reset

## Stashing & Temporary Work
- git stash saves uncommitted changes
- git stash pop reapplies and removes stash
- Useful for switching branches without committing unfinished work

## History Inspection
- git log, git show <commit>, git blame <file>
- git bisect - find commit that introduced a bug
- git reflog - local reference log of HEAD moves
- git ls-tree and git cat-file -p for low-level inspection

## .git Directory & Object Model
- .git holds objects (blobs, trees, commits) and refs
- Blob - file content
- Tree - directory snapshot
- Commit - points to tree + metadata
- Index (staging area) stored in .git/index

## Remotes & Collaboration
- git remote add origin <url> - set remote
- git fetch - download remote changes without merging
- git pull --rebase - fetch and rebase local commits
- git push origin <branch>
- git push --force-with-lease safer than --force

## Submodules & Subtrees
- Submodule - embeds another Git repo at a specific commit (git submodule add, update)
- Subtree - merges external projects into subdirectory but keeps history

## Best Practices
- Commit often with clear messages (one logical change per commit)
- Keep branches short-lived and focused
- Avoid rewriting public history
- Use .gitignore to avoid committing unnecessary files
- Use git bisect and git blame for debugging

## QA-specific Tips
- Version test scripts and fixtures
- Attach test results (logs, Allure reports) as CI artifacts
- Use git tag for testable release points
- Use PR templates to include test steps and QA checklist

## Common Pitfalls
- Accidentally committing secrets - use .gitignore, remove with git rm --cached, rotate secrets
- Force-pushing public branches - prefer --force-with-lease
- Large files - use Git LFS
- Confusing merge/rebase workflows - document team policy
