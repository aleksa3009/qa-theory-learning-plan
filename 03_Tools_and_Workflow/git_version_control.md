Git Version Control
1. What is Version Control?
Version control is a system that records changes to files over time so you can recall specific versions later. It allows multiple people to work on the same codebase without overwriting each other’s changes, keeps a history of changes, and helps track who made what change and why.
Benefits:
    • Track and revert changes easily
    • Collaborate safely with teammates
    • Maintain a history of project development
    • Integrate with CI/CD pipelines for automated testing

2. What is Git?
Git is a distributed version control system (DVCS). Unlike centralized version control systems (like SVN), every developer has a full copy of the repository, including its entire history.
Key features:
    • Local repository: all history and commits are on your machine
    • Branching and merging: easy to isolate work and integrate changes
    • Collaboration: sync with remote repositories (e.g., GitHub, GitLab, Bitbucket)

3. Git Workflow Basics
    1. Clone a repository: get a full copy from a remote server
       git clone https://github.com/user/repo.git
    2. Check status: see which files are changed or staged
       git status
    3. Stage changes: add files to the staging area before commit
       git add filename
       git add .  # add all changes
    4. Commit changes: save a snapshot in the local repository
       git commit -m "Descriptive commit message"
    5. Push to remote: upload local commits to the remote repository
       git push origin main
    6. Pull changes: fetch and integrate changes from remote
       git pull origin main

4. Branching & Merging
Branches allow you to develop features or fix bugs independently.
Create and switch branches
git branch feature-login   # create a branch
git checkout feature-login # switch to branch
# or shortcut: git switch feature-login
Merge branches
git checkout main
git merge feature-login
    • Conflicts may arise if the same lines of a file were changed in both branches.
    • Resolve conflicts manually, then commit.
Delete branch after merge
git branch -d feature-login

5. Remote Collaboration
    • Add a remote repository
git remote add origin https://github.com/user/repo.git
    • Fetch remote changes without merging
git fetch origin
    • Pull and merge remote changes
git pull origin main
    • Push local changes to remote
git push origin branch-name

6. Undoing Changes
    • Unstage a file
git reset HEAD filename
    • Discard local changes
git checkout -- filename
    • Revert a commit (creates a new commit that undoes changes)
git revert commit-hash
    • Reset to previous commit (destructive)
git reset --hard commit-hash

7. Useful Git Commands
Task
Command
Check current branch
git branch
See commit history
git log
See short log
git log --oneline
Compare changes
git diff
Tag a version
git tag v1.0
Show remote URLs
git remote -v
Stash changes
git stash (store uncommitted changes temporarily)
Apply stashed changes
git stash apply

8. Git for QA Engineers
    • Track test scripts: maintain history of automation code (Selenium, RestAssured).
    • Collaborate with devs: easily pull latest feature code to write or update tests.
    • Branching for experiments: test new automation approaches on a separate branch.
    • Rollback broken tests: quickly revert changes to known working state.
    • Integration with CI/CD: Jenkins/GitHub Actions can run tests on push/pull requests.

9. Best Practices
    • Write clear, descriptive commit messages.
    • Commit small, logical changes frequently.
    • Use branches for features, bug fixes, and experiments.
    • Always pull before pushing to avoid conflicts.
    • Avoid committing sensitive information or large binaries.
    • Use .gitignore to exclude unnecessary files (logs, IDE configs).

10. Git + Remote Platforms
    • GitHub/GitLab/Bitbucket: host remote repositories.
    • QA workflows:
        ◦ Fork repository → create branch → implement tests → push → open pull request → get review → merge.
    • Review CI/CD build results before merging to main branch.

11. Summary
Git is an essential tool for QA engineers working with automated tests:
    • Distributed, allowing local history and offline work.
    • Branches enable safe, isolated development.
    • Commits track history, and merges integrate features.
    • Remote repositories facilitate team collaboration.
    • Knowledge of Git commands and workflows is critical for daily QA tasks.
