# Pull Request Workflow

Pull requests provide a controlled mechanism for reviewing and integrating changes.

## Typical Flow

Developer
    |
    v
Feature Branch
    |
    v
Pull Request
    |
    +---- Code Review
    |
    +---- CI Checks
    |
    v
Approval
    |
    v
Merge into Main

## Why Pull Requests?

Pull requests provide:

- Code review
- Discussion
- Automated validation
- Controlled merging
- Change visibility
- Auditability

## Example

A developer creates a branch:

git switch -c feature/new-deployment

After making changes:

git add .
git commit -m "Add deployment workflow"

Then:

git push -u origin feature/new-deployment

The branch can then be used to create a pull request against the target branch.

## CI Integration

A pull request can trigger automated checks before merge.

For example:

Pull Request
    |
    v
GitHub Actions
    |
    v
Build / Test / Lint
    |
    v
Pass or Fail
    |
    v
Review
    |
    v
Merge

This reduces the chance of broken code reaching the main branch.
