# Git-flow lab

## Installation
- Install git-flow by following its repository steps;
- Enter a directory with git initialized;
- Initialize `git flow` in current repository;


## Commands
Command | Description
--------|------------
`git flow` | Show available `git flow` subcommands
`git flow <subcommand>` | List available subcommands
`git init` | Initialize git for current directory
`git flow init` | Initialize `git flow` for current repository
`git flow feature  start <feat-number>-<feat-description>` | Create a new feature branch and checkout to it
`git flow <subcommand> publish <branch-name-without-prefix/>` | Publish the branch
`git flow <subcommand> <branch-name-without-prefix>` | Clone and track remote branch
`git flow finish <branch-name>` | Merge current branch to develop and delete local and remote branch


## Workflow
- Initiate a branch;
- Checkout to it;
- Push it to origin;
- Work on the feature
- Add files to stage;
- Commit with a descriptive message;
- Publish the branch;
- Instead of merging a branch through a pull request or merge request to the `develop`, the PR should just be closed and the branch we just finished should be closed through `git flow`. That will automatically merge to develop and delete the branch from local and remote;
- Other devs who have the branch locally will have to remove them manually;

## Tips
- When checking out to another branch that is remote only, remember to use `git flow track` command to do so. Otherwise you would be only clonning the branch instead of clonning and tracking.

## Best practices
- Name a branch like: `<issue-id>-<issue-brief-description>`
    - `3315-page-title`
