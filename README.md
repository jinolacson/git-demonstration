# Advanced Git Commands


## 1. Reseting head changes with git reset

**Git reset** = is a powerful command that is used to `undo local changes` to
the state of a Git repo.

In this short clip example i will delete `npm-debug.log` and undo the deleted
file or any local changes using `git reset --hard HEAD`.

[Demo example](https://www.youtube.com/embed/AQQy2meSMoo?rel=0)

See also:

`git reset [--soft, --mixed] HEAD.`

`git checkout [commit-hash]`

`git revert HEAD.`

## 2. Editing most recent commit using git --ammend.

**Git ammend** = is for making modifications to the most recent commit.

In this short clip example by using `git --ammend` i will update commit message
`sssssss` with a new commit message.

[Demo example](https://www.youtube.com/embed/xkvpfdz_sdQ?rel=0)

## 3. Saving changes without commiting using stash and pop.

**Git stash** = is to save your changes as WIP (Work in Progress) and switch
branches without commiting.

**Git pop** = is to apply the top stashed element and removes it from the stack.

In this short clip example from `develop` im going to switch `master` branch
without commiting my local changes.

and using `git stash` ill set asside `file2.txt` as WIP(Work in Progress) and
using `git stash pop stash@{0}` we will re-apply again changes back to `develop`
branch .

[Demo example](https://www.youtube.com/embed/LbumxwFkYA4?rel=0)

See also:

- git stash apply

## 4. Integrating remote changes using --rebase

**Git rebase** = is one of two Git utilities that specializes in integrating
changes from one branch onto another.

In this short clip example remote repository was `updated 1 min ago` and i tried
to push my local changes, but it gives me an error saying **_You want to first
integrate the remote changes_**.

but using `git --rebase` it allows to pull and integrate remote changes, and
apply commit message `readme.md` as a `new sequence of commit`.

[Demo example](https://www.youtube.com/embed/fEfzd1XNmOs?rel=0)

## 5. Renaming local and remote branch.

In this short clip example by using `git branch -m [new-branch]` i can rename
local branch `feat/awesome-branch` into `bug/design-fix` and
`git push origin --delete feat/awesome-branch` to delete old remote branch.

[Demo example](https://www.youtube.com/embed/9_cKdQ30Up4?rel=0)

See also:

- [Renaming local and remote branch](https://multiplestates.wordpress.com/2015/02/05/rename-a-local-and-remote-branch-in-git/)

- [Deleting local and remote branch](https://koukia.ca/delete-a-local-and-a-remote-git-branch-61df0b10d323)

## 6. Applying commit onto other branch using cherry-pick.

**Git cherry pick** = in git means to choose a commit **_(pick a commit)_** from
one branch and apply it onto another.

This is in contrast with other ways such as `merge` and `rebase` which normally
apply many commits onto another branch.

In this short clip example im going to pick the commit hash
`ea337b35af703b6bbda80fee473097a0bb14e67e` from `feat_my_important_branch`
branch and integrate it into `master` branch.

[Demo example](https://www.youtube.com/embed/L8bKlNlV_Fs?rel=0)

**_Note: `git cherry-pick` is a useful tool `but not always a best practice`.
Cherry picking `can cause duplicate commits` and many scenarios where cherry
picking would work, traditional merges are preferred instead._**

Here is an example of duplicate commits after using cherry pick and merge to
`master` branch.

[Demo example](https://www.youtube.com/embed/rg5h-8lTPLY?rel=0)

## 7. Recovering deleted local branch using git reflog.

**Git reflog** = tracks any updates of branches, it serves as reference a
storage

In this short clip example i will delete `feat_my_important_branch` and display
reference using `git reflog`, using first 7 commit hash we can recreate the
deleted local branch by `git checkout -b feat_my_important_branch ea337b3`.

[Demo example](https://www.youtube.com/embed/dG-3E7LG4zM?rel=0)

See also:

- [Git reflog](http://gitready.com/intermediate/2009/02/09/reflog-your-safety-net.html)

- [Gist recover deleted branch](https://gist.github.com/jbgo/1944238)

## 8. Creating downloadable package with git tag.

**Git tag** = is generally used to capture a point in history that is used for a
marked version release (i.e. v1.0.1). _A tag is like a branch that doesn’t
change_.

We have two kinds of tag they are `Annotated` and `Lightweight` tags.

**Lightweight tags** = a tag that is attached to an existing commit. This merely
functions as a pointer to a specific commit, and as such it ‘piggybacks’ on that
commit’s hash as identification. This type of tag does not allow you to store
any information that specific to the tag.

**Annotated tags** = a tag that has its own commit hash and is, as such, stored
as a separate object in git. This tag allows you to store information that is
related to this specific tag. You can add a tag message, GPG sign it, and the
tagger is stored.

In this example video inside `master` branch im going to create an annotated
release tag `git tag -a 3.0.0 -m "my version 3.0"`, list using `git tag`, show
information using `git show 3.0.0` and push to remote master branch.

[Demo example](https://www.youtube.com/embed/DS0rhu86g1Y?rel=0)

**_Noted: tags are only created inside master branch_**

See also:

- [A Tutorial for Tagging Releases in Git](https://dev.to/neshaz/a-tutorial-for-tagging-releases-in-git-147e)

## 9. Force pushing to remote repository

**Git push force** = force remote branch integrate changes.

In this demonstration let's assume that we pushed unstable code to our remote
branch and we need to `revert` back to it's stable state which is the commit
message `Updated index.js`.

[Demo example](https://www.youtube.com/embed/b3fO7nCj_KE?rel=0)

Syntax :

`git push <remote> <branch> -f`

See also:

`git push <remote> <branch> --force`

`git push <remote> <branch> --force-with-lease`

`--force-with-lease` = Force pushing with a _"lease"_ allows the force push to
fail if there are new commits on the remote that you didn't expect (technically,
if you haven't fetched them into your remote-tracking branch yet), which is
useful if you don't want to accidentally overwrite someone else's commits that
you didn't even know about yet, and you just want to overwrite your own

- [Git push](https://www.atlassian.com/git/tutorials/syncing/git-push)

## 10. Removing not existing remotes references using --prune

**Git fetch --prune**

**Fetch** = updates local copies of remote branches so this is always safe for
your local branches

**Prune** = removes your local remote tracking branches where the branch no
longer exists on the remote.

BUT:

1. `fetch` will not update local branches (which track remote branches); if you
   want to update your local branches you still need to pull every branch.

2. `prune` will not create local branches (which track remote branches), you
   have to do this manually `git checkout -b [branch-name]`. If you want to list
   all remote branches: `git branch -a`

To update local branches which track remote branches: `git pull --all`

In this example i will delete `origin/feat/deleted_branch` branch directly in
github and update local remote refs using `--prune`.

[Demo example](https://www.youtube.com/embed/ogo9JDpobZI?rel=0)

Syntax:

`git fetch --prune`

See also:

`git fetch --all`
