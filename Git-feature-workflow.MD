# Adding Code to the Main Branch

All changes to a repository's main branch should be done through a feature branch, and merged into the main branch via a pull request.

## TL;DR

```bash
git checkout main
git pull
git checkout -b feature-thing-im-working-on
git diff
git add <path/name of changed file>
git commit -m 'short, meaningful commit message'
git push -u origin feature-thing-im-working-on
```
Create the pull request.

## Detailed steps for adding changes to the `main` branch

1. Make sure you don't have any uncommitted changes
    ```bash
    git status
    ```
    If this returns one or more of these lines, you need to commit or revert the changes before continuing.
    ```
    Changes not staged for commit:
    Changes to be committed:
    Untracked files:
    ```
    __DO NOT EVER COMMIT CHANGES TO THE MAIN BRANCH__
1. Make sure your repository is up-to-date with `origin`
    ```bash
    git checkout main
    git pull
    ```
1. Create a new local feature branch. Always start the name with `feature-`, then add a description of what you are working on
    ```bash
    git checkout -b feature-thing-im-working-on
    ```
1. Change some code
1. Commit the code
    ```bash
    git diff
    git add <path/name of changed file>
    git commit -m 'short, meaningful commit message'
    ```
1. Push your changes to `origin`
    ```bash
    git push -u origin feature-thing-im-working-on
    ```
    Once you have pushed the branch once, you can push new changes without `-u origin`
1. Create a pull request on Github
    1. When you push the new branch on the command line, Git will print the URL to create the pull request for the branch. You can also create it on the repository page:
        1. Select "Pull Requests -> New pull request"
        1. Use the "compare" dropdown to select your branch
        1. Click "Create pull request"
    1. Add a meaningful title and description
    1. Verify your changes under the "commits" at the bottom
    1. Select "Create pull request"
1. Have someone review your changes
1. Once you are ready to merge the pull request, select "Squash and merge"
    1. If the PR says "This branch has conflicts that must be resolved", see [Resolving Conflicts](#resolving-conflicts)
1. Add a commit message and click "Confirm squash and merge"

## Resolving Conflicts

If there are conflicts with your merge, you can select "Resolve Conflicts" and you will be taken to a list of files with conflicts, which will show up in the text like this:

```
<<<<<< feature-thing-im-working-on
This is my change
=======
This is someone else's change on the same line
>>>>>> main
```

1. Update the file with the appropriate changes
1. Select "Mark as resolved"
1. Select "Commit merge"
1. Continue with the steps above
