# Git

- [Git](#git)
  - [Introduction](#introduction)
  - [Git Workflow](#git-workflow)
  - [Key Commands](#key-commands)

## Introduction

- Git is a command-line interface (CLI) version control tool, used to create snapshots of a repository.
- It differs from GitHub, which is an online platform for code hosting, collaboration, CI/CD, and more.
- However, Git and GitHub are often used together to streamline development and collaboration.

## Git Workflow

A Git project involves three main parts:

- **Working Directory:** Where files are created, modified, and organised.
- **Staging Area:** Where changes made in the working directory are listed and prepared for the next commit.
- **Repository:** The permanent storage where Git saves different versions of the project.

The typical Git workflow involves editing files in the working directory, adding them to the staging area, and then committing changes to the repository.

## Key Commands

```bash
git init          # Initialises a new Git repository in the current directory

git status        # Displays the current state of the repository (e.g., changes to be committed, untracked files)

git diff filename # Shows the differences between the working directory and the staging area for the specified file

git add filename  # Adds changes in the working directory to the staging area

git commit -m "commit message" # Creates a new version of the project with changes from the staging area

git log           # Displays the commit history for the repository

git branch        # Lists all branches in the repository

git checkout branch-name # Switches to the specified branch

git merge branch-name    # Merges the specified branch into the current branch

git pull          # Fetches and integrates changes from a remote repository into the current branch

git push          # Uploads local changes to a remote repository

git clone repository-url  # Creates a local copy of a remote repository

git remote -v     # Displays the remote repository URLs associated with the local repository
