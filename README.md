git-scripts
===========

Collection of git-related scripts

## Installation

Simply add git-scripts/bin to your PATH.

## git-prune-branches

Removes fully-merged branches and branches that have been deleted from
upstream remotes. Interactively prompts for confirmation.

    git-prune-branches

## git-diff-base

Shows the diffs between the current branch and the merge-base from
which it came. Passes through all command line arguments to `git
diff`.

For example:

    git-diff-base

To override the "master" branch:

    MASTER=origin/master git-diff-base

To show diff --stat instead of the full diff:

    git-diff-base --stat

## git-change-author

Go through the commit log and change the author attribution for all
commits with email `old_email` to full name `new_author` with email
`new_email`.

    git-change-author <old_email> <new_author> <new_email>

For example:

    git-change-author bozo@clownsforhire.com "Bozo Clown" bozo@clown.io

Any additional command line arguments are passed to `git
filter-branch`. This enables limiting the scope of the change to
selected commits:

    git-change-author bozo@clownsforhire.com "Bozo Clown" bozo@clown.io HEAD^4..HEAD


