# rComply-Gitflow-Example
A visual example of what rComply would look like with Gitflow

# Branches

### Source Branches
Source branches are persistent and always active.
### `master`
This is the holy grail, the default branch, also known as main in some repos. The HEAD of `master` will _always_ be the latest version of production. `hotfix/` branches may be created from `master`, explained below in Supporting Branches.

Note that no commits are **ever** made straight to `master`, and every `hotfix/` branch or `release/` branch will get merged into master when complete.

### `develop`
Here is the holy grail for developers - it's in the name! The HEAD of `develop` will always represent the latest _completed_ development changes. `feature/` branches and `release/` branches may be created from `develop`, explained below in Supporting Branches.

Note that no commits are **ever** made straight to `develop`, and _every_ supporting branch (`feature/`, `release/`, and `hotfix/`) will get merged into `develop` when complete.

<p align="center"><img width=60.5% src="https://github.com/RJET-DEV/rComply-Gitflow-Example/blob/master/media/MasterAndDevelop.png"></p>


### Supporting Branches
Supporting branches are not persistent - they are created with `branch/` syntax and, once merged, are deleted.
### `feature/`
These branches will be the most common, created by branching from `develop` and named with the format `feature/COM365-867`. At any given time there may be multiple `feature/` branches active. `feature/` branches are only merged into `develop` when completed.
> Starting the name of a `feature/` branch with the case number allows it to be picked up by Jira, but it can include a description after that, i.e. `feature/COM365-867-fix-jennys-number`

<p align="center"><img width=60.5% src="https://github.com/RJET-DEV/rComply-Gitflow-Example/blob/master/media/DevelopAndFeatures.png"></p>

### `release/`
When the changes in `develop` are approved for a release, a `release/` branch is created from `develop` and named with the format `release/5.30.9`. This branch will contain tags when the version is released to DEV and QA. `release/` branches are merged into `develop` and `master` when completed, and `master` is tagged with the official version number.
> Tags on `release/` branches should have the format `DEV-5.30.9` and `QA-5.30.9`. Tags on the `master` branch should have the format `5.30.9`.

<p align="center"><img width=60.5% src="https://github.com/RJET-DEV/rComply-Gitflow-Example/blob/master/media/ReleaseBranch.png"></p>

### `hotfix/`
When an urgent or minimal-risk change is needed in production, a `hotfix/` branch can be made. `hotfix/` is the only branch type that can be created from `master`. `hotfix/` branches are merged into `master` and `develop` when completed, and `master` is tagged with the official patch number.
> After a `hotfix/` branch is merged, the convention is to increase the `master` version tag by one patch number, i.e. from `7.8.8` to `7.8.9`.

<p align="center"><img width=60.5% src="https://github.com/RJET-DEV/rComply-Gitflow-Example/blob/master/media/HotfixBranch.png"></p>
