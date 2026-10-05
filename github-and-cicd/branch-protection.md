# Branch Protection

Branch protection rules can be used to prevent unsafe changes from being merged directly into important branches.

## Example Rules

A protected main branch can require:

- Pull requests
- At least one approving review
- Passing status checks
- Restrictions on direct pushes

## Workflow

Developer
    |
    v
Feature Branch
    |
    v
Pull Request
    |
    +---- Required CI
    |
    +---- Required Review
    |
    v
Merge into main

## Why Protect Main?

The main branch generally represents a stable or releasable state.

Protection provides guardrails so that changes are reviewed and validated before they become part of that branch.

## Important Concept

Branch protection does not replace CI or code review.

It combines them into a controlled process:

Protection
    +
Review
    +
CI
    =
Safer Integration

The repository was also used to understand required approvals and collaborator permissions for protected branches.
