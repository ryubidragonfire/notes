This makes sure that your new branch is based on base-branch-name

`git checkout base-branch-name`

Create a new branch based on `base-branch-name`

`git checkout -b my-new-branch`

To show remote origin:

`git remote show origin`

To update the Pull Request with additional changes, edit your files in your branch - then, commit the changes and push them to GitHub:
```
git checkout NAME_OF_YOUR_BRANCH
# Make changes, stage all changes for commit
git add --all .
# Commit
git commit
# Push to GitHub
git push
```

If you want to update your Pull Request without creating a new commit, you can "amend" your last commit. To do so, call git commit with the --amend parameter and force-push the result to GitHub, overwriting the previous version.

```
git checkout NAME_OF_YOUR_BRANCH
# Make changes, stage all changes for commit
git add --all .
# Commit
git commit --amend
# Push to GitHub
git push -f
```

# Syncing Your Fork

After some time, you'll find that your fork has become out of sync with the upstream repository (as others add case studies and they get merged in). To sync your fork up, you just need to do a local merge and then push those changes. 

```
# Get all of the latest from upstream for all branches
git fetch upstream
# Now make sure you're on gh-pages - the main branch for this project
git checkout gh-pages
# Merge in the changes from upstream (note: this commits locally)
git merge upstream/gh-pages
# And then push those to your fork on GitHub
git push
```
