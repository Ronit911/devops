# GitHub Workflow

GitHub was used as the central platform for source control, collaboration, pull requests, CI/CD, and deployment automation.

## Repository Workflow

A typical workflow is:

Developer
    |
    v
Local Git Repository
    |
    v
GitHub Branch
    |
    v
Pull Request
    |
    v
Review + CI
    |
    v
Merge
    |
    v
Deployment

## Branches

Different branches can represent different stages of development.

Example:

main
  |
  +---- development
  |          |
  |          +---- feature branches
  |
  +---- release branches

The exact branching model depends on the team's release process.

## Remote Repository

The remote repository allows multiple developers and automation systems to work from the same source.

Useful commands include:

git remote -v

git branch

git branch -a

git fetch origin

## Collaboration

GitHub adds collaboration features around Git, including:

- Pull requests
- Reviews
- Discussions
- Issue tracking
- Branch protection
- Actions
- Repository permissions

This makes GitHub more than just a remote Git repository; it becomes part of the overall software delivery workflow.
