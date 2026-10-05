# Git Workflow

Git was used as the source control system throughout the DevOps work.

## Core Workflow

A basic Git workflow is:

Working Directory
    |
    v
git add
    |
    v
Staging Area
    |
    v
git commit
    |
    v
Local Repository
    |
    v
git push
    |
    v
GitHub Repository

## Repository Setup

A repository can be cloned using:

git clone <repository-url>

Move into the repository:

cd <repository>

Check the current state:

git status

## Common Operations

Create a branch:

git switch -c feature/example

Stage changes:

git add <file>

Commit changes:

git commit -m "Describe the change"

Push a branch:

git push origin <branch>

Download remote changes:

git fetch origin

Update the current branch:

git pull

View history:

git log --oneline

## Why Version Control Matters

Version control provides:

- Change tracking
- Collaboration
- Rollback capability
- Branching
- Code review
- Release history
- Integration with CI/CD systems

The DevOps workflow depends on source control as the starting point for automated software delivery.
