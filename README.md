# Git-flow lab

## Installation
- Install git-flow by following its repository steps;
- Enter a directory with git initialized;
- Initialize `git flow` in current repository;


## Commands
Command | Description
--------|------------
`git init` | Initialize git for current directory
`git branch -d <branch-name>` | Delete branch
`git branch -m <old-name> <new-name>` | Rename branch
`git flow` | Show available `git flow` subcommands
`git flow <subcommand>` | List available subcommands
`git flow init` | Initialize `git flow` for current repository
`git flow feature start <feat-number>-<feat-description>` | Create a new feature branch and checkout to it
`git flow <subcommand> publish <branch-name-without-prefix/>` | Publish the branch
`git flow track <branch-name-without-prefix>` | Clone and track remote branch
`git flow <subcommand> finish <branch-name-without-prefix>` | Merge current branch to develop and delete local and remote branch
`git flow release start <release-name>` | Create a release branch



## Workflow
- Initiate a feature branch;
    - `git flow feature start 2-make-background-red`
- Work on the feature
- Add files to stage;
- Commit with a descriptive message;
- Publish the branch;
    - `git flow feature publish 2-make-background-red`
- Instead of merging a branch through a pull request or merge request to the `develop`, the PR should just be closed and the branch we just finished should be closed through `git flow`. That will automatically merge to develop and delete the branch from local and remote;
    - Other devs who have the branch locally will have to remove them manually;
    - `git flow feature finish 2-make-background-red`
- Create a release branch
    - `git flow release start sprint1-release`
- Publish the `release branch`
    - `git flow release publish sprint1-release`
- QA tests...

## Observations
- When checking out to another branch that is remote only, remember to use `git flow track` command to do so. Otherwise you would be only clonning the branch instead of clonning and tracking.
- The tests are ran on the `release branch`;
    - Release branches born from the `develop branch`;
    - Any bugs found on the `release branch` must be fixed ON the `release branch` and once everything is working fine it must be merged back to the develop;
    - REMEMBER WHEN CHECKING OUT TO DEVELOP:
        - FIRST: `git pull`
        - `git merge <branch-to-be-merged-into-develop>`
        - `git push`

## Best practices
- Name a branch like: `<issue-id>-<issue-brief-description>`
    - `3315-page-title`