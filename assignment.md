## Content

### What is the difference between push, pull, and fetch?

- `git push` - send changes from a local branch to a remote repo
- `git fetch` - get changes from a remote repo into your tracking branch
- `git pull` - will get changes from a remote branch into your tracking branch and merge them into a local branch

#### `git push`
`git push` takes your current branch and checks to see whether or not there is a tracking branch for a remote repository connected to it. If so, your changes are taken from your branch and pushed to the remote branch. This is how you share your code with a remote repository.

If your remote branch has diverged from your local branch, this operation can fail. This can happen if your local branch is missing commits made in the remote branch. When this happens, your local branch needs to be synchronized with the remote branch with `git pull`, or `git fetch` and `git merge`.

#### `git fetch` 
`git fetch` checks your current branch, and tries to match it with a corresponding tracking branch. It then pulls changes into the tracking branch. It does not change your local branch. To do that, you'll need to use `git merge origin/master` (for the "master" branch) to merge those changes into your branch - probably also called "master".

#### `git pull`
`git pull` combines `git fetch` with `git merge`. In other words, `git pull` applies changes from the remote branch to the local branch. Instead, you can choose to use `git fetch` followed by `git merge` to preview changes you are merging into your branch.

### Atomic commits
Atomic commits refer to small commits that are focused on solving or resolving one issue. You should be able to describe changes made in the atomic commits with a short message.