# GitHub Basics

## 1. What is GitHub?

GitHub is a web-based platform for hosting Git repositories. It provides
tools for collaboration, version control, issue tracking, code review,
and CI/CD integration.

It is widely used for: - Hosting project code - Sharing code with
teammates or the public - Managing contributions and reviews -
Automating workflows with GitHub Actions

## 2. Repositories

A repository (repo) is a project folder containing all code, history,
branches, and configuration.

-   Can be public or private\
-   Key components:
    -   **README.md** --- project description\
    -   **.gitignore** --- excluded files\
    -   **LICENSE** --- usage rights

## 3. Key GitHub Features

-   **Branches** --- isolated development\
-   **Pull Requests (PRs)** --- propose changes, discuss, review\
-   **Issues** --- track bugs and tasks\
-   **Actions** --- automation pipelines\
-   **Wiki** --- documentation

## 4. Basic Workflow

1.  **Fork & clone repository**

        git clone https://github.com/user/repo.git

2.  **Create a new branch**

        git checkout -b feature-branch

3.  **Make changes & commit**

        git add .
        git commit -m "Add login test cases"

4.  **Push branch**

        git push origin feature-branch

5.  **Open a Pull Request**

    -   Compare branch → main
    -   Add reviewers, description

6.  **Review & merge**

    -   Approve PR
    -   Merge
    -   Delete branch (optional)

## 5. Collaboration Tips for QA

-   Pull latest changes before work:

        git pull origin main

-   Add screenshots in PR if needed
-   Use issues to report bugs
-   Follow branch naming conventions

## 6. Summary

GitHub is essential for QA to: - Host automation scripts
- Create branches for test development
- Use pull requests for collaboration
- Track bugs via Issues
- Run tests via GitHub Actions
