# My Opinionated Guide to All Things Git for All People


## Some Useful terms

origin
branch
pull request
merge

## Cloning a repository


## Making Changes to a Repository

See [Git feature workflow](Git-feature-workflow.MD)

## GitHub Settings

In your repository settings, set the following options:

* Pull Requests
    * Unselect "Allow merge commits" and "Allow rebase merging"
* Select "Automatically delete head branches"
    * This deletes feature branches after a merge

These options require a paid account:

* Under "Branches -> Add Branch ruleset"
    * Name the ruleset
    * Enforcement Status -> Select "Active"
    * Branch targeting criteria -> Add Target -> Include default branch
    * Select the following:
        * Restrict updates
        * Restrict deletions
        * Require linear history
        * Require a pull request before merging
            * Required approvals (1? 2? Depends on you)
            * Allowed merge methods
                * ONLY allow "Squash"
        * Require status checks to pass
            * Require branches to be up to date before merging
            * Do not require status checks on creation
        * Block force pushes
