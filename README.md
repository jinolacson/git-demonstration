# Git Flow

- [Boom Camp - Git Flow](https://github.com/boomcamp/git-flow)


### External Resources

- [A successful Git branching model](https://nvie.com/posts/a-successful-git-branching-model/)



<object data="presentations/Git Branch Modeling.pdf" type="application/pdf" width="700px" height="700px">
    <embed src="presentations/Git Branch Modeling.pdf">
        <p>Git Branch Modeling.pdf <a href="presentations/Git Branch Modeling.pdf">Download PDF</a>.</p>
    </embed>
</object>




<object data="presentations/Git Branch Modeling.pdf" type="application/pdf" width="700px" height="700px">
    <embed src="presentations/GIT COMMANDS.pdf">
        <p>GIT COMMANDS.pdf <a href="presentations/GIT COMMANDS.pdf">Download PDF</a>.</p>
    </embed>
</object>


# Advance Git commands

> It covers most commonly used advance commands in git. 

Covers:

1. Reseting head changes using `reset`.

2. Editing recent commit using `--ammend`.

3. Saving changes without commiting using `stash` and `pop`.

4. Integrating remote changes using `--rebase`.

5. Renaming local and remote branch.

6. Applying commit onto other branch using `cherry-pick`.

7. Recovering deleted local branch using `git reflog`.

8. Creating downloadable package using `git tag`.


TODO:

1. Setting up ssh keys.
2. Force pushing using `git push --force`.
3. Fetching only single branch from remote repository using `git fetch`.


### 1. Reseting head changes using `git reset`

**Git reset**

Git reset is a powerful command that is used to undo local changes to the state of a Git repo.

In this short clip example im going to delete `npm-debug.log` and undo deleted file or any local changes using `git reset --hard head`.

<Short video clip>

See also:

- git reset [--soft, --mixed] HEAD.

- git checkout [commit-hash] 

- git revert HEAD.


### 2. Editing most recent commit using `git --ammend`.

**Git ammend**

Git ammend is to make modifications to the most recent commit.

In this short clip example by using `git --ammend` im going to update commit message `sssssss`.

<Short video clip>


### 3. Saving changes without commiting using `stash` and `pop`.

**Git stash** and **Git pop**

- Git stashing is to save your changes as WIP (Work in Progress) and switch branches without commiting.

- Git pop is to apply the top stashed element and removes it from the stack.

In this short clip example from `develop` im going to switch to `master` branch without commiting my local changes. 

and using `git stash` ill set asside `file2.txt` as WIP(Work in Progress) and re-apply again to `develop` branch using `git stash pop stash@{0}`.

<Short video clip>

See also:

- git stash apply


### 4. Integrating remote changes using `--rebase`

**Git rebase**

Git rebase is one of two Git utilities that specializes in integrating changes from one branch onto another.

In this short clip example the github repository was `updated 1 min ago` and i tried to push my local changes back to remote repository, but it gives me an error saying "You want to first integrate the remote changes".

using `git --rebase` i can pull and integrate remote changes, and apply my commit `readme.md` as a `new sequence of commit`.

<Short video clip>


### 5. Renaming local and remote branch.

In this short clip example using `git branch -m [new-branch]` i rename local branch `feat/awesome-branch` into `bug/design-fix` and delete old remote branch using `git push origin --delete feat/awesome-branch`.

<Short video clip>


See also:

- [Renaming local and remote branch](https://multiplestates.wordpress.com/2015/02/05/rename-a-local-and-remote-branch-in-git/)

- [Deleting local and remote branch](https://koukia.ca/delete-a-local-and-a-remote-git-branch-61df0b10d323)


### 6. Applying commit onto other branch using `cherry-pick`.

**Git cherry pick**

Cherry picking in Git means to choose a commit from one branch and apply it onto another.

This is in contrast with other ways such as `merge` and rebase which normally apply many commits onto another branch.


In this short clip example im going to pick commit hash `ea337b35af703b6bbda80fee473097a0bb14e67e` from `feat_my_important_branch` and integrate it into `master` branch.

<Short video clip>

Note: `git cherry-pick` is a useful tool `but not always a best practice`. Cherry picking `can cause duplicate commits` and many scenarios where cherry picking would work, traditional merges are preferred instead.


Example of duplicate commits after cherry picking.

<Short video clip>


### 7. Recovering deleted local branch using `git reflog`.

**Git reflog**

Git reflog tracks any updates of branches, it serves as reference a storage

In this short clip example im going to delete `feat_my_important_branch`, list using `git reflog` and recreate the branch by its first 7 commit hash using `git checkout -b feat_my_important_branch ea337b3`.

<Short video clip>

See also:

- [Git reflog](http://gitready.com/intermediate/2009/02/09/reflog-your-safety-net.html)

- [Recover deleted branch](https://gist.github.com/jbgo/1944238)


### 8. Creating downloadable package using `git tag`.

**Git tag**

Git tagging is generally used to capture a point in history that is used for a marked version release (i.e. v1.0.1). *A tag is like a branch that doesn’t change*.

In this example video inside `master` branch im going to create annotated release tag `git tag -a 3.0.0 -m "my version 3.0"`, list using `git tag`, show information using `git show 3.0.0` and push to remote master branch.

<Short video clip>

Annotated vs Lightweight tags

**Lightweight tags** A tag that is attached to an existing commit. This merely functions as a pointer to a specific commit, and as such it ‘piggybacks’ on that commit’s hash as identification. This type of tag does not allow you to store any information that specific to the tag.

**Annotated tags** A tag that has its own commit hash and is, as such, stored as a separate object in git. This tag allows you to store information that is related to this specific tag. You can add a tag message, GPG sign it, and the tagger is stored.

See also:

- [A Tutorial for Tagging Releases in Git](https://dev.to/neshaz/a-tutorial-for-tagging-releases-in-git-147e)


